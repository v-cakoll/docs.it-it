---
title: Combinazione di protocolli trust in scenari federati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7031e222b152bfa61e13e0e4a44b5ad9418b07c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="85b8d-102">Combinazione di protocolli trust in scenari federati</span><span class="sxs-lookup"><span data-stu-id="85b8d-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="85b8d-103">In alcuni scenari i client federati comunicano con un servizio e con un servizio token di sicurezza che non hanno la stessa versione Trust.</span><span class="sxs-lookup"><span data-stu-id="85b8d-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="85b8d-104">Il WSDL del servizio può contenere un'asserzione `RequestSecurityTokenTemplate` con elementi WS-Trust di versioni diverse rispetto al servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="85b8d-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="85b8d-105">In tali casi, un client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] converte gli elementi WS-Trust ricevuti da `RequestSecurityTokenTemplate` affinché corrispondano alla versione Trust del servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="85b8d-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="85b8d-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le versioni Trust non corrispondenti vengono gestite solo per le associazioni standard.</span><span class="sxs-lookup"><span data-stu-id="85b8d-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="85b8d-107">Tutti i parametri dell'algoritmo standard riconosciuti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fanno parte del binding standard.</span><span class="sxs-lookup"><span data-stu-id="85b8d-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="85b8d-108">In questo argomento viene descritto il comportamento di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con le varie impostazioni di trust tra il servizio e il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="85b8d-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="85b8d-109">Componente febbraio 2005 e servizio token di sicurezza febbraio 2005</span><span class="sxs-lookup"><span data-stu-id="85b8d-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="85b8d-110">Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="85b8d-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="85b8d-111">Il file di configurazione client contiene un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="85b8d-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="85b8d-112">Poiché [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non è in grado di distinguere i parametri del client da quelli del servizio e viceversa, li aggiunge tutti e li invia in `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="85b8d-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="85b8d-113">Componente Trust 1.3 e servizio token di sicurezza Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="85b8d-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="85b8d-114">Il WSDL per il componente contiene gli elementi seguenti all'interno della sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="85b8d-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="85b8d-115">Il file di configurazione client contiene un elemento `secondaryParameters` che esegue il wrapping dei parametri specificati dal componente.</span><span class="sxs-lookup"><span data-stu-id="85b8d-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="85b8d-116"> rimuove gli elementi `EncryptionAlgorithm`, `CanonicalizationAlgorithm` e `KeyWrapAlgorithm` dall'elemento di primo livello sotto RST se sono presenti nell'elemento `SecondaryParameters`.</span><span class="sxs-lookup"><span data-stu-id="85b8d-116"> removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="85b8d-117"> aggiunge l'elemento `SecondaryParameters` al token RST non modificato in uscita.</span><span class="sxs-lookup"><span data-stu-id="85b8d-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="85b8d-118">Componente Trust febbraio 2005 e servizio token di sicurezza Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="85b8d-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="85b8d-119">Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="85b8d-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="85b8d-120">Il file di configurazione client contiene un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="85b8d-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="85b8d-121">Dal file di configurazione client, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non è in grado di distinguere i parametri del servizio da quelli del client.</span><span class="sxs-lookup"><span data-stu-id="85b8d-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="85b8d-122">Di conseguenza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converte tutti i parametri in uno spazio dei nomi della versione Trust 1.3.</span><span class="sxs-lookup"><span data-stu-id="85b8d-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="85b8d-123"> gestisce gli elementi `KeyType`, `KeySize` e `TokenType` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="85b8d-123"> handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="85b8d-124">Scaricare il WSDL, creare il binding e assegnare `KeyType`, `KeySize` e `TokenType` dai parametri del componente.</span><span class="sxs-lookup"><span data-stu-id="85b8d-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="85b8d-125">Viene quindi generato il file di configurazione client.</span><span class="sxs-lookup"><span data-stu-id="85b8d-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="85b8d-126">Il client è ora in grado di modificare qualsiasi parametro nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="85b8d-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="85b8d-127">In fase di esecuzione, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copia tutti i parametri specificati nella sezione `AdditionalTokenParameters` del file di configurazione client eccetto `KeyType`, `KeySize` e `TokenType`, poiché tali parametri vengono gestiti durante la generazione del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="85b8d-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="85b8d-128">Componente Trust 1.3 e servizio token di sicurezza Trust febbraio 2005</span><span class="sxs-lookup"><span data-stu-id="85b8d-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="85b8d-129">Il WSDL per il componente contiene i seguenti elementi nella sezione `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="85b8d-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="85b8d-130">Il file di configurazione client contiene un elemento `secondaryParamters` che esegue il wrapping dei parametri specificati dal componente.</span><span class="sxs-lookup"><span data-stu-id="85b8d-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="85b8d-131"> copia tutti i parametri specificati all'interno della sezione `SecondaryParameters` nell'elemento RST di primo livello, ma non li converte nello spazio dei nomi WS-Trust 2005.</span><span class="sxs-lookup"><span data-stu-id="85b8d-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
