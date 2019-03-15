---
title: Configurazione della serializzazione in un servizio del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 0e0f03a30aa8e8679cf849aa75948e0bc2314fe5
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57843930"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurazione della serializzazione in un servizio del flusso di lavoro
Servizi flusso di lavoro sono servizi Windows Communication Foundation (WCF) e quindi avere la possibilità di usare uno di <xref:System.Runtime.Serialization.DataContractSerializer> (predefinito) o il <xref:System.Xml.Serialization.XmlSerializer>. Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione. Quando si creano servizi del flusso di lavoro WCF non si specificano questi contratti nel codice, ma piuttosto si generano in fase di runtime dall'inferenza del contratto. Per altre informazioni sull'inferenza del contratto, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.  
  
 ![Impostazione della proprietà SerializerOption nella finestra Proprietà.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
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
  
  È possibile specificare tipi noti anche sui servizi del flusso di lavoro. Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](data-contract-known-types.md). È possibile specificare i tipi noti nella finestra di progettazione o nel codice. Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con puntini di sospensione accanto alla proprietà KnownTypes nella **finestra delle proprietà** per un <xref:System.ServiceModel.Activities.Receive> attività come illustrato nella figura seguente.   
  
 ![Screenshot della finestra di dialogo Proprietà KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Verrà visualizzato l'Editor di insiemi di tipo che consente di cercare e specificare i tipi noti.  
  
 ![Schermata dell'Editor di insiemi di tipo.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Scegliere il **Aggiungi nuovo tipo** collegare e usare il menu a discesa per selezionare o cercare un tipo da aggiungere alla raccolta di tipi noti. Per specificare i tipi noti nel codice, utilizzare la proprietà <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, come mostrato nell'esempio riportato di seguito.  
  
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
