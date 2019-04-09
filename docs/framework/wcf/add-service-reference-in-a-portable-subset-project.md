---
title: Aggiungere un riferimento al servizio in un progetto di subset portabili
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: e1d65df46c0ed6d9d271727ad04a661c5e34a1ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145431"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="10ea0-102">Aggiungere un riferimento al servizio in un progetto di subset portabili</span><span class="sxs-lookup"><span data-stu-id="10ea0-102">Add Service Reference in a Portable Subset Project</span></span>
<span data-ttu-id="10ea0-103">Progetti di subset portabili consentono ai programmatori di assembly .NET gestire un unico albero di origine e di sistema di compilazione supportando comunque più implementazioni di .NET (desktop, Silverlight, Windows Phone e XBOX).</span><span class="sxs-lookup"><span data-stu-id="10ea0-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and XBOX).</span></span> <span data-ttu-id="10ea0-104">Progetti di subset portabili fanno riferimento solo a librerie portabili .NET che sono un assembly di .NET framework che può essere usato in qualsiasi implementazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="10ea0-104">Portable subset projects only reference .NET portable libraries which are a .NET framework assembly that can be used on any .NET implementation.</span></span>  
  
## <a name="add-service-reference-details"></a><span data-ttu-id="10ea0-105">Dettagli relativi a Aggiungi riferimento al servizio</span><span class="sxs-lookup"><span data-stu-id="10ea0-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="10ea0-106">Quando si aggiunge un riferimento al servizio in un progetto di subset portabili, si applicano le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ea0-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1.  <span data-ttu-id="10ea0-107">Per l'oggetto <xref:System.Xml.Serialization.XmlSerializer> sono consentite solo le codifiche letterali.</span><span class="sxs-lookup"><span data-stu-id="10ea0-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="10ea0-108">Le codifiche SOAP generano un errore durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="10ea0-108">SOAP encodings generate an error during import.</span></span>  
  
2.  <span data-ttu-id="10ea0-109">Per i servizi che utilizzano gli scenari <xref:System.Runtime.Serialization.DataContractSerializer>, viene fornito un surrogato del contratto dati per assicurarsi che i tipi riutilizzati provengano solo dal subset portabile.</span><span class="sxs-lookup"><span data-stu-id="10ea0-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3.  <span data-ttu-id="10ea0-110">Gli endpoint che si basano su associazioni non supporte nelle librerie portabili (tutte le associazioni tranne <xref:System.ServiceModel.BasicHttpBinding>, l'oggetto <xref:System.ServiceModel.WSHttpBinding> senza flusso di transazione, le sessioni affidabili o la codifica MTOM e le associazioni personalizzate equivalenti) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="10ea0-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4.  <span data-ttu-id="10ea0-111">Le intestazioni dei messaggi vengono eliminate da tutte le descrizioni dei messaggi in tutte le operazioni prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="10ea0-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5.  <span data-ttu-id="10ea0-112">Gli attributi non portabili <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute> e <xref:System.ServiceModel.TransactionFlowAttribute> vengono rimossi dal codice del proxy client generato.</span><span class="sxs-lookup"><span data-stu-id="10ea0-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6.  <span data-ttu-id="10ea0-113">Le proprietà non portabili ProtectionLevel, SessionMode, IsInitiating, IsTerminating vengono rimosse dagli oggetti <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute> e <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10ea0-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7.  <span data-ttu-id="10ea0-114">Tutte le operazioni del servizio vengono create come operazioni asincrone nel proxy client.</span><span class="sxs-lookup"><span data-stu-id="10ea0-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8.  <span data-ttu-id="10ea0-115">I costruttori client generati che utilizzano i tipi non portabili vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="10ea0-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="10ea0-116">Un'istanza dell'oggetto <xref:System.Net.CookieContainer> viene esposta nel client generato.</span><span class="sxs-lookup"><span data-stu-id="10ea0-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="10ea0-117">Nella parte superiore del file che identifica l'assembly e la versione del generatore di codice viene inserito un commento:</span><span class="sxs-lookup"><span data-stu-id="10ea0-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:</span></span>`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`  
  
11. <span data-ttu-id="10ea0-118">L'interfaccia <xref:System.Runtime.Serialization.ISerializable> non è supportata.</span><span class="sxs-lookup"><span data-stu-id="10ea0-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="10ea0-119">Le associazioni Net.Tcp e PollingDuplex non sono supportate</span><span class="sxs-lookup"><span data-stu-id="10ea0-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="10ea0-120">L'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> verrà sempre utilizzato per gli errori.</span><span class="sxs-lookup"><span data-stu-id="10ea0-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> <span data-ttu-id="10ea0-121">non è supportato nei progetti di subset portabili.</span><span class="sxs-lookup"><span data-stu-id="10ea0-121">is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ea0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ea0-122">See also</span></span>

- [<span data-ttu-id="10ea0-123">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="10ea0-123">Accessing Services Using a WCF Client</span></span>](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="10ea0-124">Libreria di classi portabile</span><span class="sxs-lookup"><span data-stu-id="10ea0-124">Portable Class Library</span></span>](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
