---
title: Aggiungere un riferimento al servizio in un progetto di subset portabili
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: 8bedfb44523b4f67845d40fadfaa72d64622ba26
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449478"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="7a4f6-102">Aggiungere un riferimento al servizio in un progetto di subset portabili</span><span class="sxs-lookup"><span data-stu-id="7a4f6-102">Add Service Reference in a Portable Subset Project</span></span>

<span data-ttu-id="7a4f6-103">I progetti di subset portabili consentono ai programmatori di assembly .NET di mantenere un singolo albero di origine e il sistema di compilazione, supportando comunque più implementazioni .NET (desktop, Silverlight, Windows Phone e Xbox).</span><span class="sxs-lookup"><span data-stu-id="7a4f6-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and Xbox).</span></span> <span data-ttu-id="7a4f6-104">I progetti di subset portabili fanno riferimento solo a librerie portabili che sono assembly .NET che possono essere usati in qualsiasi implementazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-104">Portable subset projects only reference portable libraries that are .NET assemblies that can be used on any .NET implementation.</span></span>
  
## <a name="add-service-reference-details"></a><span data-ttu-id="7a4f6-105">Dettagli relativi a Aggiungi riferimento al servizio</span><span class="sxs-lookup"><span data-stu-id="7a4f6-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="7a4f6-106">Quando si aggiunge un riferimento al servizio in un progetto di subset portabili, si applicano le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a4f6-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1. <span data-ttu-id="7a4f6-107">Per l'oggetto <xref:System.Xml.Serialization.XmlSerializer> sono consentite solo le codifiche letterali.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="7a4f6-108">Le codifiche SOAP generano un errore durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-108">SOAP encodings generate an error during import.</span></span>  
  
2. <span data-ttu-id="7a4f6-109">Per i servizi che utilizzano gli scenari <xref:System.Runtime.Serialization.DataContractSerializer>, viene fornito un surrogato del contratto dati per assicurarsi che i tipi riutilizzati provengano solo dal subset portabile.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3. <span data-ttu-id="7a4f6-110">Gli endpoint che si basano su associazioni non supporte nelle librerie portabili (tutte le associazioni tranne <xref:System.ServiceModel.BasicHttpBinding>, l'oggetto <xref:System.ServiceModel.WSHttpBinding> senza flusso di transazione, le sessioni affidabili o la codifica MTOM e le associazioni personalizzate equivalenti) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4. <span data-ttu-id="7a4f6-111">Le intestazioni dei messaggi vengono eliminate da tutte le descrizioni dei messaggi in tutte le operazioni prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5. <span data-ttu-id="7a4f6-112">Gli attributi non portabili <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute> e <xref:System.ServiceModel.TransactionFlowAttribute> vengono rimossi dal codice del proxy client generato.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6. <span data-ttu-id="7a4f6-113">Le proprietà non portabili ProtectionLevel, SessionMode, IsInitiating, IsTerminating vengono rimosse dagli oggetti <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute> e <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7. <span data-ttu-id="7a4f6-114">Tutte le operazioni del servizio vengono create come operazioni asincrone nel proxy client.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8. <span data-ttu-id="7a4f6-115">I costruttori client generati che utilizzano i tipi non portabili vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="7a4f6-116">Un'istanza dell'oggetto <xref:System.Net.CookieContainer> viene esposta nel client generato.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="7a4f6-117">All'inizio del file viene inserito un commento che identifica l'assembly e la versione del generatore di codice:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span><span class="sxs-lookup"><span data-stu-id="7a4f6-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span></span>  
  
11. <span data-ttu-id="7a4f6-118">L'interfaccia <xref:System.Runtime.Serialization.ISerializable> non è supportata.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="7a4f6-119">Le associazioni Net.Tcp e PollingDuplex non sono supportate</span><span class="sxs-lookup"><span data-stu-id="7a4f6-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="7a4f6-120">L'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> verrà sempre utilizzato per gli errori.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <span data-ttu-id="7a4f6-121">La proprietà <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> non è supportata nei progetti di subset portabili.</span><span class="sxs-lookup"><span data-stu-id="7a4f6-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4f6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a4f6-122">See also</span></span>

- [<span data-ttu-id="7a4f6-123">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="7a4f6-123">Accessing Services Using a WCF Client</span></span>](accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="7a4f6-124">Libreria di classi portabile</span><span class="sxs-lookup"><span data-stu-id="7a4f6-124">Portable Class Library</span></span>](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
