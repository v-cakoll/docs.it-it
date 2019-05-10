---
title: 'Procedura: Condividere i dati associati tra moduli usando il componente BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 026b5456134be531b05e75474bcad6bbd46dc7fc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630470"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Procedura: Condividere i dati associati tra moduli usando il componente BindingSource
È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>. Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati. L'esempio illustra questo scenario.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form. In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio. Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.  
  
> [!NOTE]
>  Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati Per altre informazioni sui motivi per cui questa operazione viene eseguita, vedere [come: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati](../multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Componente BindingSource](bindingsource-component.md)
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Procedura: Gestire errori ed eccezioni che si verificano con il Data Binding](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
