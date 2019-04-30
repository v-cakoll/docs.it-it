---
title: Opzioni di ridimensionamento nel controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 6d100fb17b1ee3e652985a637d333d9f65e20d36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970989"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Opzioni di ridimensionamento nel controllo DataGrid
Sono disponibili per controllare diverse opzioni come la <xref:System.Windows.Controls.DataGrid> ridimensionato in modo. Il <xref:System.Windows.Controls.DataGrid>le singole righe e colonne di <xref:System.Windows.Controls.DataGrid>, può essere impostato su ridimensionati automaticamente in base al contenuto o può essere impostato su valori specifici. Per impostazione predefinita, il <xref:System.Windows.Controls.DataGrid> aumentando e riducendo per adattarsi alla dimensione del relativo contenuto.  
  
## <a name="sizing-the-datagrid"></a>Ridimensionamento di DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Precauzioni quando si usa il ridimensionamento automatico  
 Per impostazione predefinita, il <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> proprietà delle <xref:System.Windows.Controls.DataGrid> sono impostate su <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML) e il <xref:System.Windows.Controls.DataGrid> regolerà per le dimensioni del relativo contenuto.  
  
 Quando viene inserita in un contenitore che limita le dimensioni dei relativi elementi figlio, ad esempio un <xref:System.Windows.Controls.Canvas> oppure <xref:System.Windows.Controls.StackPanel>, il <xref:System.Windows.Controls.DataGrid> estenderanno oltre i limiti del contenitore visibili e non verranno visualizzate le barre di scorrimento. Questa condizione influisce sia l'usabilità e le prestazioni.  
  
 Quando associato a un set di dati, se il <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Controls.DataGrid> non è limitato, continuerà aggiungere una riga per ogni elemento di dati nel set di dati associato. Ciò può causare il <xref:System.Windows.Controls.DataGrid> possono estendersi oltre i limiti di visibilità dell'applicazione quando si aggiungono righe. Il <xref:System.Windows.Controls.DataGrid> non visualizzerà le barre di scorrimento in questo caso poiché relativo <xref:System.Windows.FrameworkElement.Height%2A> continuerà ad aumentare per includere le nuove righe.  
  
 Per ogni riga in cui viene creato un oggetto di <xref:System.Windows.Controls.DataGrid>. Se si lavora con grandi set di dati e si consente il <xref:System.Windows.Controls.DataGrid> ridimensionamento automatico, la creazione di un numero elevato di oggetti può ridurre le prestazioni dell'applicazione.  
  
 Per evitare questi problemi quando si lavora con grandi set di dati, è consigliabile impostare in modo specifico il <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Controls.DataGrid> o inserirlo in un contenitore che limita relativo <xref:System.Windows.FrameworkElement.Height%2A>, ad esempio un <xref:System.Windows.Controls.Grid>. Quando la <xref:System.Windows.FrameworkElement.Height%2A> è limitata, il <xref:System.Windows.Controls.DataGrid> verranno create solo le righe che possono essere contenuti all'interno della proprietà specificata <xref:System.Windows.FrameworkElement.Height%2A>e viene riciclato tali righe in base alle esigenze per visualizzare i nuovi dati.  
  
### <a name="setting-the-datagrid-size"></a>Impostazione delle dimensioni del controllo DataGrid  
 Il <xref:System.Windows.Controls.DataGrid> può essere impostato su ridimensionamento automatico entro i limiti specificati, o <xref:System.Windows.Controls.DataGrid> può essere impostato su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare il <xref:System.Windows.Controls.DataGrid> dimensioni.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Imposta un'altezza specifica per il <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Imposta il limite superiore per l'altezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> si estenderà verticalmente fino a raggiungere questa altezza.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Imposta il limite inferiore per l'altezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> verrà compattato in verticale fino a raggiungere questa altezza.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Imposta una larghezza specifica per il <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Imposta il limite superiore per la larghezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> aumenteranno in orizzontale fino a raggiungere questa larghezza.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Imposta il limite inferiore per la larghezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> verrà compattato in orizzontale fino a raggiungere questa larghezza.|  
  
## <a name="sizing-rows-and-row-headers"></a>Dimensionamento di righe e le intestazioni di riga  
  
### <a name="datagrid-rows"></a>Righe di DataGrid  
 Per impostazione predefinita, un <xref:System.Windows.Controls.DataGrid> della riga <xref:System.Windows.FrameworkElement.Height%2A> è impostata su <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), e l'altezza della riga verrà espanso alle dimensioni del relativo contenuto. L'altezza di tutte le righe di <xref:System.Windows.Controls.DataGrid> può essere specificato impostando il <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> proprietà. Gli utenti possono modificare l'altezza della riga trascinando i separatori di intestazione di riga.  
  
### <a name="datagrid-row-headers"></a>Intestazioni di riga DataGrid  
 Per visualizzare le intestazioni di riga, il <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. Per impostazione predefinita, vengono visualizzate le intestazioni di riga e vengono ridimensionate automaticamente per adattarsi al contenuto. Le intestazioni di riga è possibile assegnare una larghezza specifica, impostando il <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="sizing-columns-and-column-headers"></a>Ridimensionamento di colonne e intestazioni di colonna  
  
### <a name="datagrid-columns"></a>DataGrid (colonne)  
 Il <xref:System.Windows.Controls.DataGrid> Usa i valori del <xref:System.Windows.Controls.DataGridLength> e il <xref:System.Windows.Controls.DataGridLengthUnitType> struttura per specificare le modalità di ridimensionamento automatico o assoluto.  
  
 Nella tabella seguente mostra i valori forniti dal <xref:System.Windows.Controls.DataGridLengthUnitType> struttura.  
  
|Nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Il valore predefinito di dimensioni delle modalità di ridimensionamento automatico <xref:System.Windows.Controls.DataGrid> colonne in basano al contenuto delle celle e le intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|L'oggetto automatico basato sulle celle dimensioni delle modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle celle nella colonna, senza includere le intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|L'oggetto automatico basato su intestazione dimensioni delle modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne basano sul contenuto di solo le intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Il pixel basato su dimensioni delle modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne in base al valore numerico fornito.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|La modalità di ridimensionamento a stella viene utilizzata per distribuire lo spazio disponibile in base alle proporzioni ponderati.<br /><br /> In XAML, i valori asterisco sono espresse come n * dove n rappresenta un valore numerico. 1\* equivale a \*. Se, ad esempio, due colonne in una <xref:System.Windows.Controls.DataGrid> aveva larghezze dei \* e 2\*, la prima colonna riceverebbe una parte dello spazio disponibile e la seconda colonna riceverebbe due porzioni dello spazio disponibile.|  
  
 Il <xref:System.Windows.Controls.DataGridLengthConverter> classe può essere utilizzata per convertire i dati tra i valori numerici e stringa e <xref:System.Windows.Controls.DataGridLength> valori.  
  
 Per impostazione predefinita, il <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>e il <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Quando la modalità di ridimensionamento è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, colonne aumenterà la larghezza del contenuto visibile più ampio. Durante lo scorrimento, queste modalità di ridimensionamento causerà colonne da espandere se il contenuto che è maggiore di quanto si scorre la dimensione della colonna corrente nella visualizzazione. La colonna non compatterà dopo che il contenuto è di fuori della visualizzazione.  
  
 Colonne di <xref:System.Windows.Controls.DataGrid> può inoltre essere impostato su automaticamente le dimensioni solo all'interno dei limiti specificati, o le colonne possono essere impostate su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare le dimensioni delle colonne.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per una singola colonna. Esegue l'override di <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per una singola colonna. Esegue l'override di <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per una singola colonna. Esegue l'override di <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Intestazioni delle colonne DataGrid  
 Per impostazione predefinita, <xref:System.Windows.Controls.DataGrid> vengono visualizzate le intestazioni di colonna. Per nascondere le intestazioni di colonna, il <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. Per impostazione predefinita, quando vengono visualizzate le intestazioni di colonna, vengono ridimensionate automaticamente per adattarsi al contenuto. Le intestazioni di colonna è possibile assegnare un'altezza specifica, impostando il <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> proprietà.  
  
### <a name="resizing-with-the-mouse"></a>Il ridimensionamento con il Mouse  
 Gli utenti possono ridimensionare <xref:System.Windows.Controls.DataGrid> righe e colonne trascinando i separatori di intestazione di riga o colonna. Il <xref:System.Windows.Controls.DataGrid> supporta anche il ridimensionamento automatico di righe e colonne facendo doppio clic sul divisore di intestazione di riga o colonna. Per evitare che un utente di ridimensionare le colonne particolare, impostare il <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà `false` per le singole colonne. Per impedire agli utenti di ridimensionare tutte le colonne, impostare il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà `false`. Per impedire agli utenti di ridimensionare tutte le righe, impostare il <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> proprietà `false`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
