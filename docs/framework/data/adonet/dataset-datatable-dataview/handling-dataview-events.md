---
title: Gestione di eventi DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: c36c68b0375e7d03aac36de7d02b2c9579ea9316
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784596"
---
# <a name="handling-dataview-events"></a>Gestione di eventi DataView
Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>. Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio. L'evento **ListChanged** invia inoltre una notifica all'utente se l'elenco di righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di un nuovo ordinamento o di un filtro.  
  
 L'evento **ListChanged** implementa il <xref:System.ComponentModel> delegato ListChangedEventHandler dello spazio dei nomi e accetta come input <xref:System.ComponentModel.ListChangedEventArgs> un oggetto. È possibile determinare il tipo di modifica che si è verificata usando il <xref:System.ComponentModel.ListChangedType> valore di enumerazione nella proprietà **ListChangedType** dell'oggetto **ListChangedEventArgs** . Per le modifiche che comportano l'aggiunta, l'eliminazione o lo spostamento di righe, è possibile accedere al nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata utilizzando la proprietà **newIndex** dell'oggetto **ListChangedEventArgs** . Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando la proprietà **OldIndex** dell'oggetto **ListChangedEventArgs** .  
  
 **DataViewManager** espone inoltre un evento **ListChanged** per notificare all'utente se una tabella è stata aggiunta o rimossa o se è stata apportata una modifica alla raccolta **Relations** del **set di dati**sottostante.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un gestore eventi **ListChanged** .  
  
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

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [DataView](dataviews.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
