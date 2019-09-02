---
title: Gestione di eventi DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b3a1077bff9bf457b4aef0b05357d4a9260f8973
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204818"
---
# <a name="handling-dataview-events"></a>Gestione di eventi DataView
Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>. Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio. L'evento **ListChanged** invia inoltre una notifica all'utente se l'elenco di righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di un nuovo ordinamento o di un filtro.  
  
 L'evento **ListChanged** implementa il <xref:System.ComponentModel> delegato ListChangedEventHandler dello spazio dei nomi e accetta come input <xref:System.ComponentModel.ListChangedEventArgs> un oggetto. È possibile determinare il tipo di modifica che si è verificata usando il <xref:System.ComponentModel.ListChangedType> valore di enumerazione nella proprietà **ListChangedType** dell'oggetto **ListChangedEventArgs** . Per le modifiche che comportano l'aggiunta, l'eliminazione o lo spostamento di righe, è possibile accedere al nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata utilizzando la proprietà **newIndex** dell'oggetto **ListChangedEventArgs** . Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando la proprietà **OldIndex** dell'oggetto **ListChangedEventArgs** .  
  
 **DataViewManager** espone inoltre un evento **ListChanged** per notificare all'utente se una tabella è stata aggiunta o rimossa o se è stata apportata una modifica alla raccolta Relations del **set di dati**sottostante.  
  
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
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
