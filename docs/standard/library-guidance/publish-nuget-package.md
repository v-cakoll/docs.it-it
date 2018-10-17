---
title: Pubblicazione di un pacchetto NuGet
description: Le procedure consigliate per la pubblicazione di librerie .NET in NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370050"
---
# <a name="publishing-a-nuget-package"></a>Pubblicazione di un pacchetto NuGet

I pacchetti NuGet sono pubblicati e utilizzati da repository di pacchetti. Anche se NuGet.org è più ampiamente repository noti e usato, esistono molte opzioni per pubblicare i pacchetti NuGet:

* **[NuGet.org](https://www.nuget.org/)**  è il repository principale in linea per i pacchetti NuGet. Tutti i pacchetti in NuGet.org sono disponibili pubblicamente per tutti gli utenti. Per impostazione predefinita, Visual Studio con NuGet.org come origine del pacchetto e per molti sviluppatori NuGet.org è l'unico repository di pacchetti che interagiscono con. NuGet.org è il modo migliore per pubblicare i pacchetti stabili e pacchetti di versioni non definitive che si desidera includere commenti e suggerimenti della community.

* **[MyGet](https://myget.org/)**  repository del servizio supporta [feed di pacchetti personalizzati gratuito per progetti open source](https://www.myget.org/opensource). Un feed personalizzato pubblico MyGet è il posto ideale per pubblicare i pacchetti di versioni non definitive creati dal servizio di integrazione continua. MyGet fornisce inoltre feed privati in commercio.

* Oggetto **[feed locale](/nuget/hosting-packages/local-feeds)** consente di trattare una cartella, ad esempio un repository di pacchetti e rende il `*.nupkg` file nella cartella accessibile da NuGet. Un feed locale è utile per testare un pacchetto NuGet prima di pubblicarlo in NuGet.org.

> [!NOTE]
> NuGet.org [non consente di eliminare un pacchetto](/nuget/policies/deleting-packages) dopo il caricamento. Un pacchetto può essere rimossa dall'elenco in modo che non è visibile pubblicamente nell'interfaccia utente, ma il `*.nupkg` può ancora essere scaricato durante il ripristino. Inoltre, nuget.org non supporta le versioni dei pacchetti duplicati. Per correggere un pacchetto NuGet con un errore che è necessario rimuovere il pacchetto corretto dall'elenco, incrementare il numero di versione e pubblicare una nuova versione del pacchetto.

**ESEGUIRE ✔️** [pubblicare i pacchetti stabili e pacchetti di versioni non definitive](/nuget/create-packages/publish-a-package) desiderati ai suggerimenti della community a NuGet.org.

**Provare a ✔️** pubblicazione di pacchetti di versioni non definitive in MyGet un feed da una compilazione di integrazione continua.

**Provare a ✔️** test dei pacchetti nell'ambiente di sviluppo tramite un feed locale o MyGet. Controllare il funzionamento del pacchetto, quindi pubblicarlo in NuGet.org.

## <a name="nugetorg-security"></a>Sicurezza di NuGet.org

È importante che gli attori dannosi non può accedere all'account NuGet e caricare una versione dannosa della libreria. NuGet.org offre le notifiche di posta elettronica e l'autenticazione a due fattori quando viene pubblicato un pacchetto. Abilitare queste funzionalità dopo l'accesso a NuGet.org nel **impostazioni Account** pagina.

![testo alternativo](./media/publish-nuget-package/nuget-2fa.png "sicurezza dell'Account NuGet")

**Eseguire operazioni ✔️** usare un account Microsoft per accedere a NuGet.

**Eseguire operazioni ✔️** abilitare l'autenticazione a due fattori per l'accesso a NuGet.

**Eseguire operazioni ✔️** Abilita notifica posta elettronica quando viene pubblicato un pacchetto.

>[!div class="step-by-step"]
[Precedente](./sourcelink.md)
[Successivo](./versioning.md)
