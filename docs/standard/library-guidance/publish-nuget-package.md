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
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="2cca1-103">Pubblicazione di un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="2cca1-103">Publishing a NuGet package</span></span>

<span data-ttu-id="2cca1-104">I pacchetti NuGet sono pubblicati e utilizzati da repository di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="2cca1-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="2cca1-105">Anche se NuGet.org è più ampiamente repository noti e usato, esistono molte opzioni per pubblicare i pacchetti NuGet:</span><span class="sxs-lookup"><span data-stu-id="2cca1-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="2cca1-106">**[NuGet.org](https://www.nuget.org/)**  è il repository principale in linea per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="2cca1-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="2cca1-107">Tutti i pacchetti in NuGet.org sono disponibili pubblicamente per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2cca1-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="2cca1-108">Per impostazione predefinita, Visual Studio con NuGet.org come origine del pacchetto e per molti sviluppatori NuGet.org è l'unico repository di pacchetti che interagiscono con.</span><span class="sxs-lookup"><span data-stu-id="2cca1-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="2cca1-109">NuGet.org è il modo migliore per pubblicare i pacchetti stabili e pacchetti di versioni non definitive che si desidera includere commenti e suggerimenti della community.</span><span class="sxs-lookup"><span data-stu-id="2cca1-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="2cca1-110">**[MyGet](https://myget.org/)**  repository del servizio supporta [feed di pacchetti personalizzati gratuito per progetti open source](https://www.myget.org/opensource).</span><span class="sxs-lookup"><span data-stu-id="2cca1-110">**[MyGet](https://myget.org/)** repository service supports [free custom package feeds for open-source projects](https://www.myget.org/opensource).</span></span> <span data-ttu-id="2cca1-111">Un feed personalizzato pubblico MyGet è il posto ideale per pubblicare i pacchetti di versioni non definitive creati dal servizio di integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="2cca1-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="2cca1-112">MyGet fornisce inoltre feed privati in commercio.</span><span class="sxs-lookup"><span data-stu-id="2cca1-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="2cca1-113">Oggetto **[feed locale](/nuget/hosting-packages/local-feeds)** consente di trattare una cartella, ad esempio un repository di pacchetti e rende il `*.nupkg` file nella cartella accessibile da NuGet.</span><span class="sxs-lookup"><span data-stu-id="2cca1-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="2cca1-114">Un feed locale è utile per testare un pacchetto NuGet prima di pubblicarlo in NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="2cca1-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="2cca1-115">NuGet.org [non consente di eliminare un pacchetto](/nuget/policies/deleting-packages) dopo il caricamento.</span><span class="sxs-lookup"><span data-stu-id="2cca1-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="2cca1-116">Un pacchetto può essere rimossa dall'elenco in modo che non è visibile pubblicamente nell'interfaccia utente, ma il `*.nupkg` può ancora essere scaricato durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="2cca1-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="2cca1-117">Inoltre, nuget.org non supporta le versioni dei pacchetti duplicati.</span><span class="sxs-lookup"><span data-stu-id="2cca1-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="2cca1-118">Per correggere un pacchetto NuGet con un errore che è necessario rimuovere il pacchetto corretto dall'elenco, incrementare il numero di versione e pubblicare una nuova versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2cca1-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="2cca1-119">**ESEGUIRE ✔️** [pubblicare i pacchetti stabili e pacchetti di versioni non definitive](/nuget/create-packages/publish-a-package) desiderati ai suggerimenti della community a NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="2cca1-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="2cca1-120">**Provare a ✔️** pubblicazione di pacchetti di versioni non definitive in MyGet un feed da una compilazione di integrazione continua.</span><span class="sxs-lookup"><span data-stu-id="2cca1-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="2cca1-121">**Provare a ✔️** test dei pacchetti nell'ambiente di sviluppo tramite un feed locale o MyGet.</span><span class="sxs-lookup"><span data-stu-id="2cca1-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="2cca1-122">Controllare il funzionamento del pacchetto, quindi pubblicarlo in NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="2cca1-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="2cca1-123">Sicurezza di NuGet.org</span><span class="sxs-lookup"><span data-stu-id="2cca1-123">NuGet.org security</span></span>

<span data-ttu-id="2cca1-124">È importante che gli attori dannosi non può accedere all'account NuGet e caricare una versione dannosa della libreria.</span><span class="sxs-lookup"><span data-stu-id="2cca1-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="2cca1-125">NuGet.org offre le notifiche di posta elettronica e l'autenticazione a due fattori quando viene pubblicato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2cca1-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="2cca1-126">Abilitare queste funzionalità dopo l'accesso a NuGet.org nel **impostazioni Account** pagina.</span><span class="sxs-lookup"><span data-stu-id="2cca1-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="2cca1-127">![testo alternativo](./media/publish-nuget-package/nuget-2fa.png "sicurezza dell'Account NuGet")</span><span class="sxs-lookup"><span data-stu-id="2cca1-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="2cca1-128">**Eseguire operazioni ✔️** usare un account Microsoft per accedere a NuGet.</span><span class="sxs-lookup"><span data-stu-id="2cca1-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="2cca1-129">**Eseguire operazioni ✔️** abilitare l'autenticazione a due fattori per l'accesso a NuGet.</span><span class="sxs-lookup"><span data-stu-id="2cca1-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="2cca1-130">**Eseguire operazioni ✔️** Abilita notifica posta elettronica quando viene pubblicato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2cca1-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2cca1-131">[Precedente](./sourcelink.md)
[Successivo](./versioning.md)</span><span class="sxs-lookup"><span data-stu-id="2cca1-131">[Previous](./sourcelink.md)
[Next](./versioning.md)</span></span>
