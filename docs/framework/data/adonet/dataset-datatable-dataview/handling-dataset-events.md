---
title: Gestione di eventi dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 88ff0be43099758c076216e963d139b945936ba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652943"
---
# <a name="handling-dataset-events"></a>Gestione di eventi dataset
L'oggetto <xref:System.Data.DataSet> fornisce tre eventi: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>e <xref:System.Data.DataSet.MergeFailed>.  
  
## <a name="the-mergefailed-event"></a>Evento MergeFailed  
 L'evento dell'oggetto `DataSet` usato più di frequente è `MergeFailed`, che viene generato quando gli schemi degli oggetti `DataSet` sono in conflitto. Questo problema si verifica quando gli oggetti <xref:System.Data.DataRow> di origine e di destinazione presentano lo stesso valore di chiave primaria e la proprietà <xref:System.Data.DataSet.EnforceConstraints%2A> è impostata su `true`. Se ad esempio le colonne relative alla chiave primaria di una tabella da unire sono uguali tra le tabelle dei due oggetti `DataSet` , si verifica un'eccezione e viene generato un evento `MergeFailed` . L'oggetto <xref:System.Data.MergeFailedEventArgs> passato all'evento `MergeFailed` include una proprietà <xref:System.Data.MergeFailedEventArgs.Conflict%2A> che identifica il conflitto di schema tra i due oggetti `DataSet` e una proprietà <xref:System.Data.MergeFailedEventArgs.Table%2A> che identifica il nome della tabella in conflitto.  
  
 Nel frammento di codice riportato di seguito viene illustrato come aggiungere un gestore per l'evento `MergeFailed`.  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a>Evento Initialized  
 L'evento <xref:System.Data.DataSet.Initialized> viene generato dopo che il costruttore di `DataSet` inizializza una nuova istanza del `DataSet`.  
  
 La proprietà <xref:System.Data.DataSet.IsInitialized%2A> restituisce `true` se l'inizializzazione del `DataSet` è stata completata; in caso contrario, restituisce `false`. Il metodo <xref:System.Data.DataSet.BeginInit%2A> , che avvia l'inizializzazione di un `DataSet`, imposta <xref:System.Data.DataSet.IsInitialized%2A> su `false`. Il metodo <xref:System.Data.DataSet.EndInit%2A> , che termina l'inizializzazione del `DataSet`, lo imposta su `true`. Questi metodi vengono usati dall'ambiente di progettazione di Visual Studio per inizializzare un `DataSet` che viene utilizzato da un altro componente. Non vengono comunemente usati nel codice.  
  
## <a name="the-disposed-event"></a>Evento Disposed  
 `DataSet` è derivato dalla classe <xref:System.ComponentModel.MarshalByValueComponent> , che espone il metodo <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> e l'evento <xref:System.ComponentModel.MarshalByValueComponent.Disposed> . Il <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventi aggiunge un gestore eventi per restare in attesa dell'evento eliminato sul componente. È possibile usare la <xref:System.ComponentModel.MarshalByValueComponent.Disposed> eventi di un `DataSet` se si desidera eseguire codice quando il <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> viene chiamato il metodo. <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Rilascia le risorse usate dal <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
>  Il `DataSet` e `DataTable` oggetti ereditano da <xref:System.ComponentModel.MarshalByValueComponent> e supportano il <xref:System.Runtime.Serialization.ISerializable> interfaccia per la comunicazione remota. Si tratta degli unici oggetti ADO.NET che è possibile eseguire in remoto. Per altre informazioni, vedere [Remote Objects](https://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58).  
  
 Per informazioni sugli altri eventi disponibili quando si lavora con un `DataSet`, vedere [gestione di eventi DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) e [la gestione degli eventi DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Vedere anche
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Convalida dei dati](https://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)
- [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
