---
title: 'Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18f575e9bae37b66526d7b61a641374266ba627b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="f119c-102">Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="f119c-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>
<span data-ttu-id="f119c-103">Per connettersi a un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e comunicare con esso, un'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve disporre dei dettagli sull'indirizzo del servizio, la configurazione dell'associazione e il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="f119c-103">To connect to and communicate with a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="f119c-104">Il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ottiene in genere il contratto necessario tramite la precedente registrazione dei tipi di attributo obbligatori, ma ci sono casi in cui ciò non è possibile.</span><span class="sxs-lookup"><span data-stu-id="f119c-104">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="f119c-105">Invece che con la registrazione, il moniker può ottenere la definizione del contratto nella forma di un documento WSDL (Web Services Definition Language) tramite l'uso del parametro `wsdl` o dello scambio metadati, tramite il parametro `mexAddress`.</span><span class="sxs-lookup"><span data-stu-id="f119c-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="f119c-106">Questo consente scenari quali la distribuzione di un foglio di calcolo Excel in cui alcuni dei valori delle celle sono calcolati tramite interazioni di servizi Web.</span><span class="sxs-lookup"><span data-stu-id="f119c-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="f119c-107">In questo scenario, potrebbe non essere fattibile registrare l'assembly del contratto di servizio su tutti i client che potrebbero aprire il documento.</span><span class="sxs-lookup"><span data-stu-id="f119c-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="f119c-108">Il parametro `wsdl` o `mexAddress` consente una soluzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="f119c-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f119c-109">È necessario usare l'autenticazione reciproca per proteggersi dalla manomissione o lo spoofing di richieste e risposte.</span><span class="sxs-lookup"><span data-stu-id="f119c-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="f119c-110">In particolare, è importante per i client assicurarsi che l'endpoint di scambio metadati che sta rispondendo sia la parte attendibile prevista.</span><span class="sxs-lookup"><span data-stu-id="f119c-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f119c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f119c-111">Example</span></span>  
 <span data-ttu-id="f119c-112">In questo esempio viene illustrato l'uso del moniker servizio con un contratto MEX.</span><span class="sxs-lookup"><span data-stu-id="f119c-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="f119c-113">Un servizio con il contratto seguente viene esposto con un wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="f119c-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
```  
using System.ServiceModel;  
  
...  
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 <span data-ttu-id="f119c-114">Per creare un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il servizio remoto è possibile usare la stringa del moniker di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f119c-114">To construct a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client for the remote service the following example moniker string can be used.</span></span>  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="f119c-115">Durante l'esecuzione dell'applicazione client, il client esegue un `WS-MetadataExchange` con l'elemento `mexAddress` fornito.</span><span class="sxs-lookup"><span data-stu-id="f119c-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="f119c-116">Questa operazione potrebbe restituire dettagli sull'indirizzo, l'associazione e il contratto per diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="f119c-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="f119c-117">I parametri `address`, `contract`, `contractNamespace`, `binding` e `bindingNamespace` vengono usati per identificare il servizio designato.</span><span class="sxs-lookup"><span data-stu-id="f119c-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="f119c-118">Una volta messi in corrispondenza questi parametri, il moniker crea un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con la definizione di contratto appropriata e possono essere eseguite chiamate usando il client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], come con il contratto tipizzato.</span><span class="sxs-lookup"><span data-stu-id="f119c-118">Once those parameters have been matched, the moniker constructs a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client with the appropriate contract definition and calls can then be made using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, as with the typed contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f119c-119">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="f119c-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="f119c-120">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="f119c-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f119c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f119c-121">See Also</span></span>  
 [<span data-ttu-id="f119c-122">Procedura: Registrare e configurare un moniker servizio</span><span class="sxs-lookup"><span data-stu-id="f119c-122">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
