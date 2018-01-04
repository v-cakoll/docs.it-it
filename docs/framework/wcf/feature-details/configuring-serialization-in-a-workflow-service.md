---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8138fb94de953f133ab21cc2320e0914bc380fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="855bb-102">Configurazione della serializzazione in un servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="855bb-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="855bb-103">I servizi del flusso di lavoro sono servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che quindi dispongono della facoltà di utilizzare <xref:System.Runtime.Serialization.DataContractSerializer> (impostazione predefinita) o <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="855bb-103">Workflow services are [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="855bb-104">Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="855bb-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="855bb-105">Quando si creano servizi di flusso di lavoro di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], non si specificano questi contratti nel codice, piuttosto si generano durante il runtime dall'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="855bb-105">When creating [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="855bb-106">l'inferenza del contratto, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="855bb-106"> contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="855bb-107">Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A></span><span class="sxs-lookup"><span data-stu-id="855bb-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="855bb-108">che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="855bb-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="855bb-109">![Impostazione del serializzatore](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="855bb-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="855bb-110">Il serializzatore può essere impostato anche nel codice, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="855bb-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 <span data-ttu-id="855bb-111">È possibile specificare tipi noti anche sui servizi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="855bb-111">Known types can be specified on Workflow services as well.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="855bb-112">Nota Vedere tipi [tipi conosciuti di contratto dati](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="855bb-112"> Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="855bb-113">È possibile specificare i tipi noti nella finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="855bb-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="855bb-114">Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con i puntini di sospensione accanto alla proprietà KnownTypes nella finestra delle proprietà per un'attività <xref:System.ServiceModel.Activities.Receive>, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="855bb-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="855bb-115">![Proprietà KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="855bb-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="855bb-116">Viene visualizzato l'Editor della raccolta di tipi che consente di cercare e specificare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="855bb-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="855bb-117">![Aggiunta di tipi conosciuti](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="855bb-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="855bb-118">Fare clic su di **aggiungere nuovo tipo** collegamento e utilizzare il menu a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="855bb-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="855bb-119">Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="855bb-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```  
  
 <span data-ttu-id="855bb-120">Per vedere un esempio di codice completo che illustra come configurare la serializzazione di un servizio flusso di lavoro [formattazione di messaggi nei servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="855bb-120">To see a complete code example showing how to configure serialization for a workflow service see [Formatting messages in Workflow Services](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).</span></span>
