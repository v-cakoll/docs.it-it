---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 5076f3d377a656cb96909cf8df01591dc6ab72b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597540"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="ea64f-102">Configurazione della serializzazione in un servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ea64f-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="ea64f-103">I servizi flusso di lavoro sono servizi di Windows Communication Foundation (WCF) e pertanto possono scegliere di utilizzare l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> (impostazione predefinita) o <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="ea64f-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="ea64f-104">Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ea64f-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="ea64f-105">Quando si creano servizi del flusso di lavoro WCF, non si specificano questi contratti nel codice, ma vengono generati in fase di esecuzione in base all'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="ea64f-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="ea64f-106">Per ulteriori informazioni sull'inferenza del contratto, vedere [utilizzo di contratti nel flusso di lavoro](using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ea64f-106">For more information about contract inference, see  [Using Contracts in Workflow](using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="ea64f-107">Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A></span><span class="sxs-lookup"><span data-stu-id="ea64f-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="ea64f-108">che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="ea64f-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![Impostazione della proprietà SerializerOption nella finestra Proprietà.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="ea64f-110">Il serializzatore può essere impostato anche nel codice, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ea64f-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="ea64f-111">È possibile specificare tipi noti anche sui servizi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ea64f-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="ea64f-112">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ea64f-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="ea64f-113">È possibile specificare i tipi noti nella finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="ea64f-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="ea64f-114">Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con i puntini di sospensione accanto alla proprietà KnownTypes nella **finestra Proprietà** per un' <xref:System.ServiceModel.Activities.Receive> attività, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="ea64f-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![Screenshot della finestra di dialogo delle proprietà KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="ea64f-116">Viene visualizzato l'editor delle raccolte di tipi che consente di cercare e specificare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="ea64f-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![Screenshot dell'editor delle raccolte di tipi.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="ea64f-118">Fare clic sul collegamento **Aggiungi nuovo tipo** e utilizzare l'elenco a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="ea64f-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="ea64f-119">Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ea64f-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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
