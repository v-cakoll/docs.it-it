---
title: Modalità di riempimento delle colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], automatically resizing columns
- DataGridView control [Windows Forms], column fill mode
- data grids [Windows Forms], column fill mode
ms.assetid: b4ef7411-ebf4-4e26-bb33-aecec90de80c
ms.openlocfilehash: 43b8915efe303b6f56cd4adf5fdbd69f51b0b754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736870"
---
# <a name="column-fill-mode-in-the-windows-forms-datagridview-control"></a>Modalità di riempimento di colonna nel controllo DataGridView Windows Form
In modalità riempimento delle colonne il controllo <xref:System.Windows.Forms.DataGridView> ridimensiona automaticamente le proprie colonne in modo da occupare tutta la larghezza dell'area di visualizzazione disponibile. Il controllo non visualizza la barra di scorrimento orizzontale se non quando è necessario per mantenere la larghezza di ogni colonna uguale o maggiore al relativo valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>.  
  
 Il comportamento di ridimensionamento di ogni colonna dipende dalla proprietà <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> corrispondente. Il valore di questa proprietà viene ereditato dalla proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> della colonna o dalla proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> del controllo se il valore della colonna è <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet> (valore predefinito).  
  
 Ogni colonna può avere una diversa modalità di ridimensionamento, ma tutte le colonne con la modalità di ridimensionamento <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> condividono la larghezza dell'area di visualizzazione non usata da altre colonne. Questa larghezza viene suddivisa tra le colonne in modalità riempimento in base a proporzioni relative ai rispettivi valori della proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>. Se, ad esempio, i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> di due colonne sono 100 e 200, la prima colonna avrà larghezza dimezzata rispetto alla seconda colonna.  
  
## <a name="user-resizing-in-fill-mode"></a>Ridimensionamento da parte degli utenti in modalità riempimento  
 Diversamente dalle modalità di ridimensionamento che ridimensionano in base al contenuto delle celle, la modalità riempimento non impedisce agli utenti di ridimensionare le colonne la cui proprietà <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> è impostata su `true`. Quando un utente ridimensiona una colonna in modalità riempimento, vengono ridimensionate anche tutte le colonne in modalità riempimento dopo la colonna ridimensionata (a destra se <xref:System.Windows.Forms.Control.RightToLeft%2A> è `false`, altrimenti a sinistra) per compensare la modifica nella larghezza disponibile. Se dopo la colonna ridimensionata non sono presenti colonne in modalità riempimento, tutte le altre colonne in modalità riempimento nel controllo vengono ridimensionate per compensare la modifica. Se nel controllo non sono presenti altre colonne in modalità riempimento, il ridimensionamento viene ignorato. Se viene ridimensionata una colonna che non è in modalità riempimento, tutte le colonne in modalità riempimento nel controllo cambiano dimensioni per compensare la modifica.  
  
 Una volta ridimensionata una colonna in modalità riempimento, i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> modificati per tutte le colonne vengono adattati in proporzione. Ad esempio, se quattro colonne in modalità riempimento sono associate a valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> pari a 100 e si ridimensiona la seconda colonna in base alla metà della sua larghezza originale, i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> saranno 100, 50, 125 e 125. Se si ridimensiona una colonna che non è in modalità riempimento, non viene modificato alcun valore di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>, perché le colonne in modalità riempimento vengono semplicemente ridimensionate per compensare la modifica mantenendo le stesse proporzioni.  
  
## <a name="content-based-fillweight-adjustment"></a>Adeguamento di FillWeight in base al contenuto  
 È possibile inizializzare i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> per colonne in modalità riempimento usando i metodi di ridimensionamento automatico <xref:System.Windows.Forms.DataGridView>, ad esempio il metodo <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>. Questo metodo calcola prima di tutto le larghezze necessarie alle colonne per visualizzare il rispettivo contenuto. Il controllo adatta quindi i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> per tutte le colonne in modalità riempimento, in modo che le rispettive proporzioni corrispondano a quelle delle larghezze calcolate. Infine, il controllo ridimensiona le colonne in modalità riempimento usando le nuove proporzioni <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> in modo che tutte le colonne nel controllo occupino tutto lo spazio orizzontale disponibile.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Usando i valori appropriati per le proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>e <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A>, è possibile personalizzare i comportamenti di ridimensionamento delle colonne per molto scenari diversi.  
  
 Il codice di esempio seguente permette di sperimentare più valori per le proprietà <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> e <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di colonne diverse. Nell'esempio un controllo <xref:System.Windows.Forms.DataGridView> è associato alla relativa raccolta <xref:System.Windows.Forms.DataGridView.Columns%2A> e una colonna è associata a ognuna delle proprietà <xref:System.Windows.Forms.DataGridViewColumn.HeaderText%2A>, <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>, <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>, <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> e <xref:System.Windows.Forms.DataGridViewColumn.Width%2A>. Ognuna delle colonne è anche rappresentata da una riga nel controllo e la modifica dei valori in una riga comporta l'aggiornamento delle proprietà della colonna corrispondente, in modo da mostrare l'interazione dei valori.  
  
### <a name="code"></a>Codice  
 [!code-csharp[System.Windows.Forms.DataGridViewFillColumnsDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewFillColumnsDemo/CS/fillcolumns.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewFillColumnsDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewFillColumnsDemo/vb/fillcolumns.vb#00)]  
  
### <a name="comments"></a>Comments  
 Per usare questa applicazione di esempio:  
  
- Modificare le dimensioni del form. Osservare il modo in cui cambia la larghezza delle colonne mantenendo le proporzioni indicate dai valori della proprietà <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.  
  
- Modificare le dimensioni delle colonne trascinando i separatori di colonna con il mouse. Osservare il modo in cui cambiano i valori di <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.  
  
- Modificare il valore di <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> per una colonna, quindi trascinare per ridimensionare il form. Dopo aver ridotto a sufficienza le dimensioni del form, osservare come i valori di <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> non sono mai minori dei valori di <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A>.  
  
- Modificare i valori di <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> per tutte le colonne in numeri elevati, in modo che i valori combinati superino la larghezza del controllo. Osservare il modo in cui viene visualizzata la barra di scorrimento orizzontale.  
  
- Modificare i valori di <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A>per alcune colonne. Osservare l'effetto del ridimensionamento delle colonne o del form.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=nameWithType>
- [Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
