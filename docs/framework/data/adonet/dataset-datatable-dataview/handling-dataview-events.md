---
title: Gestione di eventi DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 2f30a578c5233e8b86a165dd220efd45348c5042
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43541094"
---
# <a name="handling-dataview-events"></a>Gestione di eventi DataView
Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>. Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio. Il **ListChanged** evento invierà una notifica se l'elenco di righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di una nuova sequenza di ordinamento o filtro.  
  
 Il **ListChanged** evento implementa le **ListChangedEventHandler** delegare del <xref:System.ComponentModel> dello spazio dei nomi e accetta come input un <xref:System.ComponentModel.ListChangedEventArgs> oggetto. È possibile determinare il tipo di modifica si è verificata utilizzando la <xref:System.ComponentModel.ListChangedType> valore di enumerazione nel **ListChangedType** proprietà del **ListChangedEventArgs** oggetto. Per le modifiche che implicano l'aggiunta, eliminazione o spostamento di righe, il nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata è accessibile tramite il **NewIndex** proprietà del **ListChangedEventArgs** oggetti. Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando il **OldIndex** proprietà delle **ListChangedEventArgs** oggetto.  
  
 Il **DataViewManager** espone anche una **ListChanged** eventi per ricevere una notifica se una tabella è stato aggiunta o rimossa oppure se è stata apportata una modifica per il **relazioni** raccolta del sottostante **set di dati**.  
  
 Esempio di codice seguente viene illustrato come aggiungere un **ListChanged** gestore dell'evento.  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
