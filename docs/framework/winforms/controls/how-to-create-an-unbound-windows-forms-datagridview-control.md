---
title: 'Procedura: Creare un controllo DataGridView di Windows non associato form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: da59f02c3f0465d330f73cfd5453d5bce58fca12
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718376"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>Procedura: Creare un controllo DataGridView di Windows non associato form
Nell'esempio di codice seguente viene illustrato come compilare un controllo <xref:System.Windows.Forms.DataGridView> a livello di codice senza associarlo a un'origine dati. Ciò è utile quando si dispone di una piccola quantità di dati che si vuole visualizzare in formato tabella.  
  
 Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Creazione di un Windows non associato di controllo DataGridView form](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  

## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- [Procedura dettagliata: Creazione di una cornice di Windows Form controllo DataGridView](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
