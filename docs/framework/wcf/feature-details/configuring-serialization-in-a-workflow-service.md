---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857508"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="08e1b-102">Configurazione della serializzazione in un servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="08e1b-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="08e1b-103">Servizi flusso di lavoro sono servizi Windows Communication Foundation (WCF) e quindi avere la possibilità di usare uno di <xref:System.Runtime.Serialization.DataContractSerializer> (predefinito) o il <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="08e1b-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="08e1b-104">Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="08e1b-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="08e1b-105">Quando si creano servizi del flusso di lavoro WCF non si specificano questi contratti nel codice, ma piuttosto si generano in fase di runtime dall'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="08e1b-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="08e1b-106">Per altre informazioni sull'inferenza del contratto, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="08e1b-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="08e1b-107">Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A></span><span class="sxs-lookup"><span data-stu-id="08e1b-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="08e1b-108">che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="08e1b-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Impostazione della proprietà SerializerOption nella finestra Proprietà.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="08e1b-110">Il serializzatore può essere impostato anche nel codice, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="08e1b-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  <span data-ttu-id="08e1b-111">È possibile specificare tipi noti anche sui servizi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="08e1b-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="08e1b-112">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="08e1b-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="08e1b-113">È possibile specificare i tipi noti nella finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="08e1b-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="08e1b-114">Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con puntini di sospensione accanto alla proprietà KnownTypes nella **finestra delle proprietà** per un <xref:System.ServiceModel.Activities.Receive> attività come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="08e1b-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>   
  
 ![Screenshot della finestra di dialogo Proprietà KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="08e1b-116">Verrà visualizzato l'Editor di insiemi di tipo che consente di cercare e specificare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="08e1b-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Schermata dell'Editor di insiemi di tipo.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="08e1b-118">Scegliere il **Aggiungi nuovo tipo** collegare e usare il menu a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="08e1b-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="08e1b-119">Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="08e1b-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```csharp
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
