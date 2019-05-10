---
title: "Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 93949f003a55cdf67c4ecde988d268728c75e081
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614689"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged
Il componente <xref:System.Windows.Forms.BindingSource> rileva automaticamente le modifiche in un'origine dati quando il tipo contenuto nell'origine dati implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> e genera eventi <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> nel momento in cui il valore di una proprietà viene modificato. Si tratta di una caratteristica utile perché i controlli associati al componente <xref:System.Windows.Forms.BindingSource> verranno aggiornati automaticamente al variare dei valori dell'origine dati.  
  
> [!NOTE]
>  Se l'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e devono essere eseguite operazioni asincrone, non devono essere apportate modifiche all'origine dati in un thread in background. In alternativa, è possibile leggere i dati in un thread in background e quindi unire i dati in un elenco nel thread dell'interfaccia utente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrata una semplice implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Viene inoltre descritto il modo in cui il componente <xref:System.Windows.Forms.BindingSource> passa automaticamente una modifica dell'origine dati a un controllo associato quando <xref:System.Windows.Forms.BindingSource> è associato a un elenco di tipo <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Se si utilizza l'attributo `CallerMemberName`, le chiamate al metodo `NotifyPropertyChanged` non devono specificare il nome della proprietà come argomento di tipo stringa. Per altre informazioni, vedere [informazioni sul chiamante (C#)](../../../csharp/programming-guide/concepts/caller-information.md) oppure [informazioni sul chiamante (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto. Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [Componente BindingSource](bindingsource-component.md)
- [Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
