
# 📦 ASP.NET Solution Template

Ce dépôt fournit un **template de solution ASP.NET en C#** permettant d'automatiser la création de nouveaux projets avec les configurations spécifiques à votre organisation.

---

## 🎯 Objectif

Standardiser et accélérer la mise en place de nouveaux projets en fournissant une base prête à l'emploi, incluant :

- Une structure de solution cohérente
- Une configuration NuGet optimisée
- Une priorisation des packages internes en cours de développement

---

## ⚙️ Configuration NuGet

Le fichier `nuget.config` est conçu pour **prioriser un flux local de packages** par rapport aux sources publiques, afin de favoriser l'utilisation de packages internes en cours de développement.

### 📄 Exemple de `nuget.config`

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>
        <clear />
        <add key="LocalFeed" value="C:\LocalNuGet" />
        <add key="Github" value="https://nuget.pkg.github.com/Microservice-Architecture-NET-A-Rename/index.json" />
        <add key="Nuget" value="https://api.nuget.org/v3/index.json" />
    </packageSources>

    <packageSourceMapping>
        <packageSource key="LocalFeed">
            <package pattern="*" />
        </packageSource>
        <packageSource key="Github">
            <package pattern="*" />
        </packageSource>
        <packageSource key="Nuget">
            <package pattern="*" />
        </packageSource>
    </packageSourceMapping>
</configuration>
```

---

## 🧠 Explication

- **`packageSources`** :
  - `LocalFeed` : Dossier local contenant les packages en développement (`C:\LocalNuGet`)
  - `Github` : Source GitHub Packages de l'organisation
  - `Nuget` : Source officielle NuGet.org

- **`packageSourceMapping`** :
  - Permet de spécifier quelle source doit être utilisée pour chaque package.
  - Ici, `LocalFeed` a la **priorité absolue** (`pattern="*"`), garantissant que les packages locaux sont utilisés avant ceux disponibles publiquement.

---

## 🚀 Mise en route

TODO

---

## ✅ Avantages

- 🔧 Base technique prête à l'emploi
- ♻️ Réutilisable dans toute l'organisation
- ⚡️ Démarrage de projet plus rapide
- 📦 Meilleure gestion des packages NuGet internes

---

## 📌 Remarques

- Le chemin `C:\LocalNuGet` est une convention. Il peut être modifié selon les besoins de votre équipe.
- Le fichier `nuget.config` doit être conservé dans le dossier `.nuget` ou à la racine de la solution pour être correctement pris en compte par Visual Studio et `dotnet`.


