---
title: 'Procedura: associare controlli Windows Form a valori di database DBNull'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: c8c942b872b23bc6ff0a6f254b952189f9e62dbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530315"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a>Procedura: associare controlli Windows Form a valori di database DBNull
Quando si associano controlli Windows Form a un'origine dati e questa restituisce un valore <xref:System.DBNull>, è possibile sostituire un valore appropriato senza gestire, formattare o analizzare eventi. La proprietà <xref:System.Windows.Forms.Binding.NullValue%2A> eseguirà la conversione del valore <xref:System.DBNull> in un oggetto specificato durante la formattazione o l'analisi dei valori dell'origine dati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come associare un valore <xref:System.DBNull> in due situazioni diverse. Nel primo caso viene dimostrato come impostare il valore <xref:System.Windows.Forms.Binding.NullValue%2A> per una proprietà di stringa e nel secondo viene dimostrato come impostare il valore <xref:System.Windows.Forms.Binding.NullValue%2A> per una proprietà di immagine.  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 I tipi della proprietà associata e la proprietà <xref:System.Windows.Forms.Binding.NullValue%2A> devono corrispondere, in caso contrario viene generato un errore e non vengono elaborati altri valori <xref:System.Windows.Forms.Binding.NullValue%2A>. In questo caso, non viene generata alcuna eccezione.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Procedura: gestire gli errori e le eccezioni che si verificano con l'associazione dati](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
