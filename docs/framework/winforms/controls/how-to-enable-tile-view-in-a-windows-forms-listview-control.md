---
title: 'Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 14eb21fa0285275e510b865c5cee7d1fc82fd0fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326996"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a>Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms
La funzionalità di visualizzazione affiancata del controllo <xref:System.Windows.Forms.ListView>, è possibile fornire un equilibrio visivo tra informazioni grafiche e testuali. Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli. La visualizzazione affiancata viene usata in combinazione con le funzionalità di raggruppamento o segno di inserimento nel controllo <xref:System.Windows.Forms.ListView>.  
  
 La visualizzazione affiancata usa un'icona di 32 x 32 pixel e alcune righe di testo, come illustrato nelle immagini seguenti.  
  
 ![Visualizzazione affiancata in un controllo ListView](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "riquadro Visualizza icone e testo")  
 
 Per abilitare la visualizzazione affiancata, impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Tile>. È possibile regolare la dimensione dei riquadri impostando la proprietà <xref:System.Windows.Forms.ListView.TileSize%2A> e il numero di righe di testo visualizzate nel riquadro regolando la raccolta <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
> [!NOTE]
>  La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
  
### <a name="to-set-tile-view-programmatically"></a>Per impostare la visualizzazione affiancata a livello di codice  
  
1. Usare l'enumerazione <xref:System.Windows.Forms.View> del controllo <xref:System.Windows.Forms.ListView>.  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a>Esempio  
 L'esempio di codice completo seguente illustra la visualizzazione affiancata con riquadri modificati in modo da visualizzare tre righe di testo. La dimensione dei riquadri è stata modificata per evitare il ritorno a capo.  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System e System.Windows.Forms.  
  
-   Un file di icona denominato book.ico nella stessa directory del file eseguibile.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
