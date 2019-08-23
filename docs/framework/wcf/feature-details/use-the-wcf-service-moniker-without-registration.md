---
title: 'Procedura: Usare il moniker del servizio di Windows Communication Foundation senza registrazione'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: 16f428b614fe331faffabab477c6584fb682801d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955238"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="ce49f-102">Procedura: Usare il moniker del servizio di Windows Communication Foundation senza registrazione</span><span class="sxs-lookup"><span data-stu-id="ce49f-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>
<span data-ttu-id="ce49f-103">Per connettersi a e comunicare con un servizio Windows Communication Foundation (WCF), un'applicazione client WCF deve disporre dei dettagli relativi all'indirizzo del servizio, alla configurazione dell'associazione e al contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce49f-103">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="ce49f-104">Il moniker del servizio WCF ottiene in genere il contratto richiesto tramite la registrazione precedente dei tipi di attributo richiesti, ma in alcuni casi non è fattibile.</span><span class="sxs-lookup"><span data-stu-id="ce49f-104">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="ce49f-105">Invece che con la registrazione, il moniker può ottenere la definizione del contratto nella forma di un documento WSDL (Web Services Definition Language) tramite l'uso del parametro `wsdl` o dello scambio metadati, tramite il parametro `mexAddress`.</span><span class="sxs-lookup"><span data-stu-id="ce49f-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="ce49f-106">Questo consente scenari quali la distribuzione di un foglio di calcolo Excel in cui alcuni dei valori delle celle sono calcolati tramite interazioni di servizi Web.</span><span class="sxs-lookup"><span data-stu-id="ce49f-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="ce49f-107">In questo scenario, potrebbe non essere fattibile registrare l'assembly del contratto di servizio su tutti i client che potrebbero aprire il documento.</span><span class="sxs-lookup"><span data-stu-id="ce49f-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="ce49f-108">Il parametro `wsdl` o `mexAddress` consente una soluzione autonoma.</span><span class="sxs-lookup"><span data-stu-id="ce49f-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce49f-109">È necessario usare l'autenticazione reciproca per proteggersi dalla manomissione o lo spoofing di richieste e risposte.</span><span class="sxs-lookup"><span data-stu-id="ce49f-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="ce49f-110">In particolare, è importante per i client assicurarsi che l'endpoint di scambio metadati che sta rispondendo sia la parte attendibile prevista.</span><span class="sxs-lookup"><span data-stu-id="ce49f-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce49f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce49f-111">Example</span></span>  
 <span data-ttu-id="ce49f-112">In questo esempio viene illustrato l'uso del moniker servizio con un contratto MEX.</span><span class="sxs-lookup"><span data-stu-id="ce49f-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="ce49f-113">Un servizio con il contratto seguente viene esposto con un wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="ce49f-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
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
  
 <span data-ttu-id="ce49f-114">Per costruire un client WCF per il servizio remoto, è possibile usare la stringa del moniker di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ce49f-114">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="ce49f-115">Durante l'esecuzione dell'applicazione client, il client esegue un `WS-MetadataExchange` con l'elemento `mexAddress` fornito.</span><span class="sxs-lookup"><span data-stu-id="ce49f-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="ce49f-116">Questa operazione potrebbe restituire dettagli sull'indirizzo, l'associazione e il contratto per diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="ce49f-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="ce49f-117">I parametri `address`, `contract`, `contractNamespace`, `binding` e `bindingNamespace` vengono usati per identificare il servizio designato.</span><span class="sxs-lookup"><span data-stu-id="ce49f-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="ce49f-118">Una volta che tali parametri sono stati confrontati, il moniker costruisce un client WCF con la definizione del contratto appropriata e le chiamate possono essere eseguite utilizzando il client WCF, come nel contratto tipizzato.</span><span class="sxs-lookup"><span data-stu-id="ce49f-118">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ce49f-119">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="ce49f-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="ce49f-120">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="ce49f-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce49f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce49f-121">See also</span></span>

- [<span data-ttu-id="ce49f-122">Procedura: Registrare e configurare un moniker servizio</span><span class="sxs-lookup"><span data-stu-id="ce49f-122">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
