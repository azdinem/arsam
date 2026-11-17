<script>
    import "../app.css";
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import CookieManager from "$lib/components/CookieManager.svelte";

    let { children } = $props();

    const schemaOrg = {
        "@context": "https://schema.org",
        "@type": "ProfessionalService",
        "name": "Arsaam Studio",
        "url": "https://arsaam-studio.com",
        "logo": "https://arsaam-studio.com/og-image.png",
        "image": "https://arsaam-studio.com/og-image.png",
        "description": "Arsaam Studio, studio de design graphique d'Anwar Benkerta, graphiste à Montpellier : identité visuelle, logo, charte graphique et webdesign.",
        "email": "arsaam.studio@gmail.com",
        "founder": {
            "@type": "Person",
            "name": "Anwar BENKERTA",
            "jobTitle": "Graphiste"
        },
        "address": {
            "@type": "PostalAddress",
            "addressLocality": "Montpellier",
            "postalCode": "34080",
            "addressRegion": "Occitanie",
            "addressCountry": "FR"
        },
        "sameAs": [
            "https://www.instagram.com/arsaamstudio/",
            "https://www.linkedin.com/in/anwar-benkerta",
            "https://www.malt.fr/profile/anwarbenkerta",
            "https://graphiste.com/Arsaam"
        ],
        "priceRange": "€€",
        "areaServed": [
            { "@type": "City", "name": "Montpellier" },
            { "@type": "AdministrativeArea", "name": "Montpellier Méditerranée Métropole" },
            { "@type": "City", "name": "Sète" },
            { "@type": "City", "name": "Lunel" },
            { "@type": "City", "name": "Béziers" },
            { "@type": "City", "name": "Nîmes" },
            { "@type": "AdministrativeArea", "name": "Hérault" }
        ],
        "serviceType": ["Branding", "Identité visuelle", "Webdesign", "Stratégie de marque"]
    };
</script>

<svelte:head>
    {@html `<script type="application/ld+json">${JSON.stringify(schemaOrg)}</script>`}
</svelte:head>

<Header />

<main>
    {@render children()}
</main>

<Footer />

<CookieManager />

<style>
    main {
        min-height: 80vh;
    }
</style>
