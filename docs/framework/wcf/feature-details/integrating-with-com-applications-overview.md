---
title: Panoramica sull'integrazione con applicazioni COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c283e7cbc4cb4b8bc37dd1313480410df93a93bf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596825"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="2f5f1-102">Panoramica sull'integrazione con applicazioni COM</span><span class="sxs-lookup"><span data-stu-id="2f5f1-102">Integrating with COM Applications Overview</span></span>

<span data-ttu-id="2f5f1-103">Windows Communication Foundation (WCF) fornisce allo sviluppatore del codice gestito un ambiente completo per la creazione di applicazioni connesse.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="2f5f1-104">Tuttavia, se si ha un investimento sostanziale nel codice basato su COM non gestito e non si vuole eseguire la migrazione, è comunque possibile integrare i servizi Web WCF direttamente nel codice esistente usando il moniker del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="2f5f1-105">Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>

> [!NOTE]
> <span data-ttu-id="2f5f1-106">Il moniker del servizio utilizza un canale di comunicazione WCF per tutte le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="2f5f1-107">I meccanismi di sicurezza e identità per tale canale differiscono da quelli utilizzati nei proxy COM e DCOM standard.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="2f5f1-108">Inoltre, poiché il moniker del servizio utilizza un canale di comunicazione WCF, il periodo di timeout predefinito è di un minuto per tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>

<span data-ttu-id="2f5f1-109">Il moniker del servizio viene utilizzato con la `GetObject` funzione per fornire allo sviluppatore non gestito un approccio specifico com e fortemente tipizzato per la chiamata ai servizi Web WCF.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="2f5f1-110">Questa operazione richiede una definizione locale visibile a COM del contratto del servizio Web WCF e l'associazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="2f5f1-111">Analogamente ad altri client WCF, il moniker del servizio deve creare un canale tipizzato per il servizio, anche se questa costruzione del canale si verifica in modo trasparente al programmatore COM sulla prima chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>

<span data-ttu-id="2f5f1-112">In comune con altri client WCF, quando si usa il moniker, le applicazioni specificano l'indirizzo, l'associazione e il contratto per comunicare con un servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="2f5f1-113">Il contratto può essere specificato in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f5f1-113">The contract can be specified in one of the following ways:</span></span>

- <span data-ttu-id="2f5f1-114">Contratto tipizzato: il contratto viene registrato come tipo visibile a COM sul computer client.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>

- <span data-ttu-id="2f5f1-115">Contratto WSDL: il contratto viene fornito sotto forma di documento WSDL.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>

- <span data-ttu-id="2f5f1-116">Contratto MEX: il contratto viene recuperato in fase di esecuzione da un endpoint MEX (Metadata Exchange).</span><span class="sxs-lookup"><span data-stu-id="2f5f1-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>

## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="2f5f1-117">Parametri supportati dal moniker del servizio</span><span class="sxs-lookup"><span data-stu-id="2f5f1-117">Parameters Supported by the Service Moniker</span></span>

<span data-ttu-id="2f5f1-118">Nella tabella seguente vengono illustrati i parametri supportati dal moniker del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-118">The following table shows the parameters that are supported by the service moniker.</span></span>

|<span data-ttu-id="2f5f1-119">Parametro</span><span class="sxs-lookup"><span data-stu-id="2f5f1-119">Parameter</span></span>|<span data-ttu-id="2f5f1-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f5f1-120">Description</span></span>|
|---------------|-----------------|
|`address`|<span data-ttu-id="2f5f1-121">Percorso URL del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-121">URL location of the service.</span></span>|
|`binding`|<span data-ttu-id="2f5f1-122">Nome della sezione dell'associazione ottenuto dalla configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-122">Binding section name from the application configuration.</span></span>|
|`bindingConfiguration`|<span data-ttu-id="2f5f1-123">Istanza dell'associazione non anonima ottenuta dall'interno la sezione dell'associazione non anonima.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-123">Named binding instance from within the named binding section.</span></span>|
|`contract`|<span data-ttu-id="2f5f1-124">Identificatore di interfaccia (IID) che rappresenta il contratto del servizio o il nome del contratto (ottenuto da MEX).</span><span class="sxs-lookup"><span data-stu-id="2f5f1-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|
|`wsdl`|<span data-ttu-id="2f5f1-125">Documento WSDL che fornisce un tipo alternativo di definizione del contratto.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-125">WSDL document that provides an alternative form of contract definition.</span></span>|
|`spnIdentity`|<span data-ttu-id="2f5f1-126">Identità del nome principale del server (SPN) da utilizzare per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|
|`upnIdentity`|<span data-ttu-id="2f5f1-127">Identità del nome di entità utente (UPN) da utilizzare per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|
|`dnsIdentity`|<span data-ttu-id="2f5f1-128">Identità DNS da utilizzare per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-128">DNS identity to be used to communicate with the service.</span></span>|
|`mexAddress`|<span data-ttu-id="2f5f1-129">Percorso URL dell'endpoint MEX (Metadata Exchange) del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|
|`mexBinding`|<span data-ttu-id="2f5f1-130">Nome della sezione dell'associazione ottenuto dalla configurazione dell'applicazione da connettere con l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|
|`mexBindingConfiguration`|<span data-ttu-id="2f5f1-131">Istanza dell'associazione non anonima ottenuta dall'interno della sezione dell'associazione non anonima da connettere con l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|
|`bindingNamespace`|<span data-ttu-id="2f5f1-132">Spazio dei nomi del nome della sezione dell'associazione ottenuto dal MEX recuperato.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-132">Namespace of the binding section name from the retrieved MEX.</span></span>|
|`contractNamespace`|<span data-ttu-id="2f5f1-133">Spazio dei nomi del contratto ottenuto dal MEX recuperato.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-133">Namespace of the contract from the retrieved MEX.</span></span>|
|`mexSpnIdentity`|<span data-ttu-id="2f5f1-134">Identità del nome principale del server (SPN) da utilizzare per comunicare con l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexUpnIdentity`|<span data-ttu-id="2f5f1-135">Identità del nome dell'entità utente (UPN) da utilizzare per comunicare con l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|
|`mexDnsIdentity`|<span data-ttu-id="2f5f1-136">Identità DNS da utilizzare per comunicare con l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|
|`serializer`|<span data-ttu-id="2f5f1-137">Consente di specificare l'utilizzo del serializzatore "xml" o "datacontract."</span><span class="sxs-lookup"><span data-stu-id="2f5f1-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|

> [!NOTE]
> <span data-ttu-id="2f5f1-138">Anche quando viene usato con client completamente basati su COM, il moniker del servizio richiede che WCF e il .NET Framework di supporto 2,0 siano installati nel computer client.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="2f5f1-139">È inoltre fondamentale che le applicazioni client che utilizzano il moniker del servizio carichino la versione appropriata del runtime .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="2f5f1-140">Quando il moniker viene utilizzato all'interno di applicazioni Office, può essere necessario un file di configurazione per garantire il caricamento della versione corretta del framework.</span><span class="sxs-lookup"><span data-stu-id="2f5f1-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="2f5f1-141">Ad esempio, con Excel, è consigliabile inserire il testo seguente in un file denominato Excel.exe.config nella stessa directory del file Excel.exe:</span><span class="sxs-lookup"><span data-stu-id="2f5f1-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> <span data-ttu-id="2f5f1-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="2f5f1-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a><span data-ttu-id="2f5f1-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f5f1-143">See also</span></span>

- [<span data-ttu-id="2f5f1-144">Procedura: registrare e configurare un moniker servizio</span><span class="sxs-lookup"><span data-stu-id="2f5f1-144">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
