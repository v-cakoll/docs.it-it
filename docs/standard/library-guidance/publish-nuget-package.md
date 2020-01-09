---
title: Pubblicazione di un pacchetto NuGet
description: Procedure consigliate per la pubblicazione delle librerie .NET in NuGet.
ms.date: 10/02/2018
ms.openlocfilehash: e567fe3f7e00bf322cdd50786e50128961107469
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706465"
---
# <a name="publishing-a-nuget-package"></a>Pubblicazione di un pacchetto NuGet

I pacchetti NuGet sono pubblicati e utilizzati dai repository di pacchetti. Anche se NuGet.org è il repository più noto e più usato, ci sono molte posizioni in cui pubblicare i pacchetti NuGet:

* **[NuGet.org](https://www.nuget.org/)** è il repository online primario per i pacchetti NuGet. Tutti i pacchetti in NuGet.org sono disponibili pubblicamente per tutti gli utenti. Per impostazione predefinita, Visual Studio ha NuGet.org come origine dei pacchetti e per molti sviluppatori NuGet.org è l'unico repository di pacchetti con cui interagiranno. NuGet.org è il luogo migliore per pubblicare pacchetti stabili e pacchetti in versione non definitiva per cui si vogliono conoscere i commenti e suggerimenti della community.

* **[MyGet](https://myget.org/)** è un servizio di repository che supporta feed di pacchetti personalizzati per progetti open source. Un feed personalizzato pubblico MyGet è il luogo ideale per pubblicare pacchetti in versione non definitiva creati dal servizio di integrazione continua. MyGet fornisce inoltre feed privati a livello commerciale.

* Un **[feed locale](/nuget/hosting-packages/local-feeds)** consente di trattare una cartella come repository di pacchetti e rende i file `*.nupkg` nella cartella accessibili tramite NuGet. Un feed locale è utile per testare un pacchetto NuGet prima di pubblicarlo in NuGet.org.

> [!NOTE]
> NuGet.org [non consente di eliminare un pacchetto](/nuget/policies/deleting-packages) dopo averlo caricato. Un pacchetto può essere rimosso dall'elenco in modo che non sia visibile pubblicamente nell'interfaccia utente, ma `*.nupkg` può essere ugualmente scaricato al momento del ripristino. Nuget.org non consente inoltre le versioni dei pacchetti duplicate. Per correggere un pacchetto NuGet con un errore, è necessario rimuovere il pacchetto non corretto dall'elenco, incrementare il numero di versione e pubblicare una nuova versione del pacchetto.

**✔️** [pubblicare pacchetti stabili e pacchetti di versioni](/nuget/create-packages/publish-a-package) non definitive per i quali si desidera inviare commenti alla community a NuGet.org.

**✔️ VALUTARE** la possibilità di pubblicare pacchetti in versione non definitiva in un feed MyGet da una build di integrazione continua.

**✔️ VALUTARE** la possibilità di testare i pacchetti nell'ambiente di sviluppo usando un feed locale o in MyGet. Controllare che il pacchetto funzioni, quindi pubblicarlo in NuGet.org.

## <a name="nugetorg-security"></a>Sicurezza di NuGet.org

È importante che attori malintenzionati non possano accedere all'account NuGet e caricare una versione dannosa della libreria. NuGet.org offre l'autenticazione a due fattori e le notifiche tramite posta elettronica quando viene pubblicato un pacchetto. Abilitare queste funzionalità dopo l'accesso a NuGet.org nella pagina **Impostazioni account**.

![testo alternativo](./media/publish-nuget-package/nuget-2fa.png "Sicurezza dell'account NuGet")

**✔️ USARE** un account Microsoft per accedere a NuGet.

**✔️ ABILITARE** l'autenticazione a due fattori per accedere a NuGet.

**✔️ ABILITARE** la notifica tramite posta elettronica quando un pacchetto viene pubblicato.

>[!div class="step-by-step"]
>[Precedente](sourcelink.md)
>[Successivo](versioning.md)
