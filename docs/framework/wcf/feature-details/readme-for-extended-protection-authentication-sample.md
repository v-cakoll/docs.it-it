---
title: File Leggimi sull'esempio relativo alla protezione estesa per l'autenticazione
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 9b0a3535282a1fcc1103651f5601459e80d3d8d4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601101"
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="0e6da-102">File Leggimi sull'esempio relativo alla protezione estesa per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="0e6da-102">ReadMe for Extended Protection Authentication Sample</span></span>

<span data-ttu-id="0e6da-103">La protezione estesa è un'iniziativa di sicurezza per la protezione da attacchi man-in-the-Middle (MITM), in cui un utente malintenzionato ("Man-in-the-the-Middle") intercetta le credenziali di un client e le usa per accedere alle risorse protette sul server previsto del client.</span><span class="sxs-lookup"><span data-stu-id="0e6da-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>

<span data-ttu-id="0e6da-104">Per ulteriori informazioni, vedere [protezione estesa per l'autenticazione Overview](extended-protection-for-authentication-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0e6da-104">For more information, see [Extended Protection for Authentication Overview](extended-protection-for-authentication-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0e6da-105">Questo esempio funziona solo quando è ospitato in IIS</span><span class="sxs-lookup"><span data-stu-id="0e6da-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="0e6da-106">e non funziona in Visual Studio Development Server perché non supporta HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0e6da-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e6da-107">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0e6da-107">To Set Up, Build, and Run the Sample</span></span>

1. <span data-ttu-id="0e6da-108">Installare IIS nel computer da installazione applicazioni-> funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="0e6da-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>

2. <span data-ttu-id="0e6da-109">Attivare l'autenticazione di Windows nelle funzionalità di Windows: Internet Information Services-> World Wide Web Services-> sicurezza-> autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0e6da-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>

3. <span data-ttu-id="0e6da-110">Attivare l'attivazione HTTP nelle funzionalità di Windows: Microsoft .NET Framework 3.5.1-> Windows Communication Foundation attivazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="0e6da-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>

4. <span data-ttu-id="0e6da-111">In questo esempio il client deve stabilire un canale protetto con il server ed è di conseguenza necessario che sia presente un certificato del server che può essere installato da Gestione Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="0e6da-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>

    1. <span data-ttu-id="0e6da-112">Aprire Gestione IIS-> certificati del server (dalla scheda visualizzazione funzionalità).</span><span class="sxs-lookup"><span data-stu-id="0e6da-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>

    2. <span data-ttu-id="0e6da-113">Ai fini dimostrativi di questo esempio, è possibile creare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="0e6da-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="0e6da-114">Se non si desidera che venga visualizzato un messaggio relativo alla sicurezza del certificato, è possibile installare un certificato presente nell'archivio Autorità di certificazione radice attendibili.</span><span class="sxs-lookup"><span data-stu-id="0e6da-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>

5. <span data-ttu-id="0e6da-115">Spostarsi sul riquadro azioni per il sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="0e6da-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="0e6da-116">Fare clic su Modifica associazioni > sito.</span><span class="sxs-lookup"><span data-stu-id="0e6da-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="0e6da-117">Aggiungere HTTPS come tipo, se non è già presente, con il numero di porta 443 e assegnare il certificato SSL creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0e6da-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>

6. <span data-ttu-id="0e6da-118">Compilare il servizio.</span><span class="sxs-lookup"><span data-stu-id="0e6da-118">Build the service.</span></span> <span data-ttu-id="0e6da-119">In questo modo viene creata automaticamente una directory virtuale in IIS (dall'azione di post-compilazione specificata nelle proprietà di progetto) e vengono copiati i file con estensione dll e svc e il file di configurazione per un servizio da ospitare nel Web.</span><span class="sxs-lookup"><span data-stu-id="0e6da-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>

7. <span data-ttu-id="0e6da-120">Aprire Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="0e6da-120">Open the IIS Manager.</span></span> <span data-ttu-id="0e6da-121">Fare clic con il pulsante destro del mouse sulla directory virtuale (ExtendedProtection) creata nel passaggio precedente, quindi scegliere Converti in applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e6da-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>

8. <span data-ttu-id="0e6da-122">Aprire il modulo di autenticazione in Gestione IIS relativo alla directory virtuale e abilitare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0e6da-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>

9. <span data-ttu-id="0e6da-123">Aprire le impostazioni avanzate per l'autenticazione di Windows relativa alla directory virtuale e specificare il valore in modo che sia richiesta poiché nell'esempio il valore ExtendedProtection corrispondente è impostata su Sempre.</span><span class="sxs-lookup"><span data-stu-id="0e6da-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>

10. <span data-ttu-id="0e6da-124">Per testare il servizio, accedere all'URL da una finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="0e6da-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="0e6da-125">Se si desidera accedere a tale URL da più computer, verificare che il firewall sia aperto per tutte le connessioni HTTP e HTTPS in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0e6da-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>

11. <span data-ttu-id="0e6da-126">Aprire il file di configurazione del client e specificare un nome di computer completo per l' \<client>  -  \<endpoint> attributo-address, sostituendo \<full_machine_name> .</span><span class="sxs-lookup"><span data-stu-id="0e6da-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing \<full_machine_name>.</span></span>

12. <span data-ttu-id="0e6da-127">Eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="0e6da-127">Run the client.</span></span> <span data-ttu-id="0e6da-128">Per comunicare con il servizio, il client stabilisce un canale protetto e utilizza la protezione estesa tra gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0e6da-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
