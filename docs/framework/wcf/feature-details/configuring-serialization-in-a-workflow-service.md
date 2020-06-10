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
# <a name="configuring-serialization-in-a-workflow-service"></a>Configurazione della serializzazione in un servizio del flusso di lavoro
I servizi flusso di lavoro sono servizi di Windows Communication Foundation (WCF) e pertanto possono scegliere di utilizzare l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> (impostazione predefinita) o <xref:System.Xml.Serialization.XmlSerializer> . Durante la scrittura dei servizi non del flusso di lavoro, il tipo di serializzatore da utilizzare viene specificato nel contratto del servizio o dell'operazione. Quando si creano servizi del flusso di lavoro WCF, non si specificano questi contratti nel codice, ma vengono generati in fase di esecuzione in base all'inferenza del contratto. Per ulteriori informazioni sull'inferenza del contratto, vedere [utilizzo di contratti nel flusso di lavoro](using-contracts-in-workflow.md).  Il serializzatore viene specificato tramite la proprietà <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> che può essere impostata come mostrato nella finestra di progettazione nell'illustrazione seguente.  
  
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
  
  È possibile specificare tipi noti anche sui servizi del flusso di lavoro. Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](data-contract-known-types.md). È possibile specificare i tipi noti nella finestra di progettazione o nel codice. Per specificare i tipi noti nella finestra di progettazione, fare clic sul pulsante con i puntini di sospensione accanto alla proprietà KnownTypes nella **finestra Proprietà** per un' <xref:System.ServiceModel.Activities.Receive> attività, come illustrato nella figura seguente.
  
 ![Screenshot della finestra di dialogo delle proprietà KnownTypes.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Viene visualizzato l'editor delle raccolte di tipi che consente di cercare e specificare i tipi noti.  
  
 ![Screenshot dell'editor delle raccolte di tipi.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
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
