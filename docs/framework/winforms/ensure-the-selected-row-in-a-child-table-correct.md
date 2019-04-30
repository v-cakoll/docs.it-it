---
title: 'Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: 891a9a4d092de35ceff2f5ceb6dbde77cf2ca2ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966954"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a>Procedura: Garantire che la riga selezionata in una tabella figlio rimanga nella posizione corretta
Quando si usa il data binding in Windows Form, spesso i dati vengono mostrati in una visualizzazione denominata padre/figlio o master/dettagli Si tratta di uno scenario di data binding in cui i dati provenienti dalla stessa origine vengono visualizzati in due controlli. Se si modifica la selezione in un controllo, automaticamente vengono modificati anche i dati visualizzati nel secondo controllo. Ad esempio, il primo controllo può contenere un elenco di clienti e il secondo un elenco di ordini correlati al cliente selezionato nel primo controllo.  
  
 A partire da .NET Framework versione 2.0, quando si visualizzano i dati in una visualizzazione padre/figlio può essere necessario effettuare alcuni passaggi aggiuntivi per assicurarsi che la riga attualmente selezionata nella tabella figlio non venga reimpostata sulla prima riga della tabella. A tale scopo, è necessario memorizzare nella cache la posizione della tabella figlio e reimpostarla dopo aver modificato la tabella padre. In genere, la tabella figlio viene reimpostata la prima volta che si modifica un campo in una riga della tabella padre.  
  
### <a name="to-cache-the-current-child-position"></a>Per memorizzare nella cache la posizione corrente della tabella figlio  
  
1. Dichiarare una variabile Integer per archiviare la posizione dell'elenco figlio e una variabile booleana per archiviare se memorizzare nella cache la posizione della tabella figlio.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2. Gestire l'evento <xref:System.Windows.Forms.CurrencyManager.ListChanged> per l'oggetto <xref:System.Windows.Forms.CurrencyManager> dell'associazione e individuare un oggetto <xref:System.ComponentModel.ListChangedType> di <xref:System.ComponentModel.ListChangedType.Reset>.  
  
3. Controllare la posizione corrente dell'oggetto <xref:System.Windows.Forms.CurrencyManager>. Se è maggiore del primo elemento dell'elenco, in genere 0, salvarlo in una variabile.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4. Gestire l'evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> dell'elenco padre per l'oggetto CurrencyManager padre. Nel gestore impostare il valore booleano per indicare che non si tratta di uno scenario di memorizzazione nella cache. Se si verifica l'evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, la modifica all'elemento padre sarà una modifica alla posizione dell'elenco e non una modifica al valore dell'elemento.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a>Per reimpostare la posizione dell'elemento figlio  
  
1. Gestire l'evento <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> per l'oggetto <xref:System.Windows.Forms.CurrencyManager> del binding figlio.  
  
2. Reimpostare la posizione della tabella figlio sulla posizione memorizzata nella cache salvata nella procedura precedente.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come salvare la posizione corrente nell'oggetto <xref:System.Windows.Forms.CurrencyManager> per una tabella figlio e reimpostare la posizione dopo aver effettuato una modifica nella tabella padre. In questo esempio sono presenti due controlli <xref:System.Windows.Forms.DataGridView> associati a due tabelle in un oggetto <xref:System.Data.DataSet> mediante un componente <xref:System.Windows.Forms.BindingSource>. Tra le due tabelle viene stabilita una relazione, che viene aggiunta all'oggetto <xref:System.Data.DataSet>. La posizione nella tabella figlio viene impostata inizialmente sulla terza riga a mero scopo esemplificativo.  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 Per testare l'esempio di codice, eseguire la procedura seguente:  
  
1. Eseguire l'esempio.  
  
2. Verificare che la casella di controllo **Memorizza nella cache e reimposta posizione** sia selezionata.  
  
3. Fare clic sul pulsante **Cancella campo padre** per provocare una modifica in un campo della tabella padre. Notare che la riga selezionata nella tabella figlio non cambia.  
  
4. Chiudere ed eseguire nuovamente l'esempio. È necessario eseguire questa procedura perché la reimpostazione si verifica solo in seguito alla prima modifica nella riga padre.  
  
5. Deselezionare la casella di controllo **Memorizza nella cache e reimposta posizione**.  
  
6. Fare clic sul pulsante **Cancella campo padre**. Notare che la riga selezionata nella tabella figlio diventa la prima riga.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.XML.  
  
 Per informazioni su come compilare questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [compilazione da riga di comando con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati](multiple-controls-bound-to-data-source-synchronized.md)
- [Componente BindingSource](./controls/bindingsource-component.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
