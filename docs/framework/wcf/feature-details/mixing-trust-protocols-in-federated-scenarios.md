---
title: Combinazione di protocolli trust in scenari federati
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
ms.openlocfilehash: d4290880d8d708811a95b38356aa61f0d23c89a8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205147"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="da41d-102">Combinazione di protocolli trust in scenari federati</span><span class="sxs-lookup"><span data-stu-id="da41d-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="da41d-103">In alcuni scenari i client federati comunicano con un servizio e con un servizio token di sicurezza che non hanno la stessa versione Trust.</span><span class="sxs-lookup"><span data-stu-id="da41d-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="da41d-104">Il WSDL del servizio può contenere un'asserzione `RequestSecurityTokenTemplate` con elementi WS-Trust di versioni diverse rispetto al servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="da41d-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="da41d-105">In questi casi, un client Windows Communication Foundation (WCF) converte gli elementi WS-Trust ricevuti dal `RequestSecurityTokenTemplate` in modo che corrisponda il servizio token di versione trust.</span><span class="sxs-lookup"><span data-stu-id="da41d-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="da41d-106">WCF gestisce le versioni trust non corrispondenti solo per le associazioni standard.</span><span class="sxs-lookup"><span data-stu-id="da41d-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="da41d-107">Tutti i parametri dell'algoritmo standard riconosciuti da WCF fanno parte dell'associazione standard.</span><span class="sxs-lookup"><span data-stu-id="da41d-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="da41d-108">In questo argomento viene descritto il comportamento WCF con varie impostazioni di trust tra il servizio e il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="da41d-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="da41d-109">Componente febbraio 2005 e servizio token di sicurezza febbraio 2005</span><span class="sxs-lookup"><span data-stu-id="da41d-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="da41d-110">Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="da41d-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="da41d-111">Il file di configurazione client contiene un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="da41d-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="da41d-112">WCF non è possibile distinguere tra il client e il servizio ha parametri. Aggiunge tutti i parametri e li invia nel `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="da41d-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="da41d-113">Componente Trust 1.3 e servizio token di sicurezza Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="da41d-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="da41d-114">Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="da41d-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="da41d-115">Il file di configurazione client contiene un elemento `secondaryParameters` che esegue il wrapping dei parametri specificati dal componente.</span><span class="sxs-lookup"><span data-stu-id="da41d-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="da41d-116">WCF rimuove il `EncryptionAlgorithm`, `CanonicalizationAlgorithm` e `KeyWrapAlgorithm` gli elementi di elemento di primo livello sotto RST se sono presenti all'interno di `SecondaryParameters` elemento.</span><span class="sxs-lookup"><span data-stu-id="da41d-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="da41d-117">WCF consente di accodare il `SecondaryParameters` elemento RST in uscita senza modificata.</span><span class="sxs-lookup"><span data-stu-id="da41d-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="da41d-118">Componente Trust febbraio 2005 e servizio token di sicurezza Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="da41d-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="da41d-119">Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="da41d-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="da41d-120">Il file di configurazione client contiene un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="da41d-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="da41d-121">Da file di configurazione del client WCF non è possibile distinguere tra i parametri del servizio e client.</span><span class="sxs-lookup"><span data-stu-id="da41d-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="da41d-122">Di conseguenza WCF converte tutti i parametri in uno spazio dei nomi versione 1.3 di Trust.</span><span class="sxs-lookup"><span data-stu-id="da41d-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="da41d-123">WCF gestisce il `KeyType`, `KeySize`, e `TokenType` elementi come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="da41d-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="da41d-124">Scaricare il WSDL, creare il binding e assegnare `KeyType`, `KeySize` e `TokenType` dai parametri del componente.</span><span class="sxs-lookup"><span data-stu-id="da41d-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="da41d-125">Viene quindi generato il file di configurazione client.</span><span class="sxs-lookup"><span data-stu-id="da41d-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="da41d-126">Il client è ora in grado di modificare qualsiasi parametro nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="da41d-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="da41d-127">Durante la fase di esecuzione, WCF consente di copiare tutti i parametri specificati nel `AdditionalTokenParameters` sezione del file di configurazione client eccetto `KeyType`, `KeySize` e `TokenType`, perché questi parametri vengono presi in considerazione durante il file di configurazione generazione.</span><span class="sxs-lookup"><span data-stu-id="da41d-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="da41d-128">Componente Trust 1.3 e servizio token di sicurezza Trust febbraio 2005</span><span class="sxs-lookup"><span data-stu-id="da41d-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="da41d-129">Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="da41d-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="da41d-130">Il file di configurazione client contiene un elemento `secondaryParamters` che esegue il wrapping dei parametri specificati dal componente.</span><span class="sxs-lookup"><span data-stu-id="da41d-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="da41d-131">WCF consente di copiare tutti i parametri specificati all'interno di `SecondaryParameters` sezione per l'elemento RST di primo livello, ma non li converte allo spazio dei nomi WS-Trust 2005.</span><span class="sxs-lookup"><span data-stu-id="da41d-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
