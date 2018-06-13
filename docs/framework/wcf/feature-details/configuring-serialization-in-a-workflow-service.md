---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 74d9a812b9e0cd51a401fa3526c947d52413807a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488872"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="6d931-102">Configurazione della serializzazione in un servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d931-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="6d931-103">Servizi flusso di lavoro sono servizi Windows Communication Foundation (WCF) e quindi avere la possibilità di usare uno di <xref:System.Runtime.Serialization.DataContractSerializer> (impostazione predefinita) o <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d931-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="6d931-104">Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="6d931-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="6d931-105">Quando si creano servizi flusso di lavoro WCF non si specificano questi contratti nel codice, ma piuttosto che vengono generati in fase di runtime dall'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="6d931-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="6d931-106">Per ulteriori informazioni sull'inferenza del contratto, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="6d931-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="6d931-107">Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A></span><span class="sxs-lookup"><span data-stu-id="6d931-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="6d931-108">che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="6d931-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6d931-109">![Impostazione del serializzatore](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="6d931-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="6d931-110">Il serializzatore può essere impostato anche nel codice, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6d931-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
 <span data-ttu-id="6d931-111">È possibile specificare tipi noti anche sui servizi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6d931-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="6d931-112">Per ulteriori informazioni sui tipi noti, vedere [tipi conosciuti di contratto dati](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="6d931-112">For more information about Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="6d931-113">È possibile specificare i tipi noti nella finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="6d931-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="6d931-114">Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con i puntini di sospensione accanto alla proprietà KnownTypes nella finestra delle proprietà per un'attività <xref:System.ServiceModel.Activities.Receive>, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="6d931-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6d931-115">![Proprietà KnownTypes](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="6d931-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="6d931-116">Viene visualizzato l'Editor della raccolta di tipi che consente di cercare e specificare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="6d931-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="6d931-117">![Aggiunta di tipi conosciuti](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="6d931-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="6d931-118">Fare clic su di **aggiungere nuovo tipo** collegamento e utilizzare il menu a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="6d931-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="6d931-119">Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6d931-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="6d931-120">Per vedere un esempio di codice completo che illustra come configurare la serializzazione di un servizio flusso di lavoro [formattazione di messaggi nei servizi flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d931-120">To see a complete code example showing how to configure serialization for a workflow service see [Formatting messages in Workflow Services](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md).</span></span>
