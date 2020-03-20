---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185342"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurazione della serializzazione in un servizio del flusso di lavoro
I servizi del flusso di lavoro sono servizi Windows Communication <xref:System.Runtime.Serialization.DataContractSerializer> Foundation (WCF) <xref:System.Xml.Serialization.XmlSerializer>e pertanto hanno la possibilità di utilizzare il (impostazione predefinita) o il . Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione. Quando si creano servizi flusso di lavoro WCF non si specificano questi contratti nel codice, ma vengono generati in fase di esecuzione dall'inferenza del contratto. Per ulteriori informazioni sull'inferenza del contratto, vedere [Utilizzo dei contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.  
  
 ![Impostazione della proprietà SerializerOption nella finestra Proprietà.Setting the SerializerOption property in the Properties Window.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 Il serializzatore può essere impostato anche nel codice, come mostrato nell'esempio seguente.  
  
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
  
  È possibile specificare tipi noti anche sui servizi del flusso di lavoro. Per ulteriori informazioni sui tipi noti, vedere [Tipi noti del contratto dati](data-contract-known-types.md). È possibile specificare i tipi noti nella finestra di progettazione o nel codice. Per specificare tipi noti nella finestra di progettazione, fare clic sul pulsante con i segusini accanto alla proprietà KnownTypes nella **finestra Proprietà** per un'attività, <xref:System.ServiceModel.Activities.Receive> come illustrato nella figura seguente.
  
 ![Screenshot della finestra di dialogo delle proprietà KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Verrà visualizzato l'Editor raccolte di tipi che consente di cercare e specificare i tipi noti.  
  
 ![Screenshot dell'Editor raccolte di tipi.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Fare clic sul collegamento **Aggiungi nuovo tipo** e utilizzare l'elenco a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti. Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.  
  
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
