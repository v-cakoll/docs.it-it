---
title: Opzioni di ridimensionamento nel controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0019ac9ad82301506d2da279094b2c96e022e915
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557849"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Opzioni di ridimensionamento nel controllo DataGrid
Sono disponibili varie opzioni per controllo come <xref:System.Windows.Controls.DataGrid> ridimensiona. Il <xref:System.Windows.Controls.DataGrid>le singole righe e colonne di <xref:System.Windows.Controls.DataGrid>, può essere impostata su dimensioni automaticamente in base al contenuto o può essere impostato su valori specifici. Per impostazione predefinita, il <xref:System.Windows.Controls.DataGrid> verrà aumentare e ridurre per adattarla alle dimensioni del relativo contenuto.  
  
## <a name="sizing-the-datagrid"></a>Ridimensionamento di DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Utilizzo di ridimensionamento automatico  
 Per impostazione predefinita, il <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> le proprietà del <xref:System.Windows.Controls.DataGrid> sono impostate su <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML) e <xref:System.Windows.Controls.DataGrid> verranno regolati a quella del relativo contenuto.  
  
 Quando viene inserita all'interno di un contenitore che non limita le dimensioni dei relativi elementi figlio, ad esempio un <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.DataGrid> verrà allungato oltre i limiti del contenitore visibili e non verranno visualizzate le barre di scorrimento. Questa condizione ha implicazioni sia usabilità e le prestazioni.  
  
 Quando è associato a un set di dati, se il <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Controls.DataGrid> non è limitato, verrà aggiunta una riga per ogni elemento dati nel set di dati associato. Ciò può causare il <xref:System.Windows.Controls.DataGrid> possono estendersi oltre i limiti di visibilità dell'applicazione quando si aggiungono righe. Il <xref:System.Windows.Controls.DataGrid> non visualizzerà le barre di scorrimento in questo caso perché il relativo <xref:System.Windows.FrameworkElement.Height%2A> continuerà ad aumentare per includere le nuove righe.  
  
 Per ogni riga in cui viene creato un oggetto di <xref:System.Windows.Controls.DataGrid>. Se si lavora con grandi set di dati e si consente il <xref:System.Windows.Controls.DataGrid> per il ridimensionamento automatico, la creazione di un numero elevato di oggetti compromettere le prestazioni dell'applicazione.  
  
 Per evitare questi problemi quando si lavora con grandi set di dati, è consigliabile impostare in modo specifico il <xref:System.Windows.FrameworkElement.Height%2A> del <xref:System.Windows.Controls.DataGrid> o inserirlo in un contenitore che limita la relativa <xref:System.Windows.FrameworkElement.Height%2A>, ad esempio un <xref:System.Windows.Controls.Grid>. Quando il <xref:System.Windows.FrameworkElement.Height%2A> è limitata, la <xref:System.Windows.Controls.DataGrid> creerà solo le righe che possono essere contenuti all'interno della proprietà specificata <xref:System.Windows.FrameworkElement.Height%2A>e riciclando le righe in base alle esigenze per visualizzare i nuovi dati.  
  
### <a name="setting-the-datagrid-size"></a>Impostazione delle dimensioni del controllo DataGrid  
 Il <xref:System.Windows.Controls.DataGrid> è possibile impostare il ridimensionamento automatico entro limiti specificati, o <xref:System.Windows.Controls.DataGrid> può essere impostato su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare il <xref:System.Windows.Controls.DataGrid> dimensioni.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Imposta un'altezza specifica per il <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Imposta il limite superiore per l'altezza di <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> si estenderà verticalmente fino a raggiungere l'altezza.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Imposta il limite inferiore per l'altezza di <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> verrà ridotto verticalmente fino a raggiungere l'altezza.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Imposta una larghezza specifica per il <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Imposta il limite superiore per la larghezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> aumenteranno orizzontalmente fino a raggiungere questa larghezza.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Imposta il limite inferiore per la larghezza del <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Controls.DataGrid> verrà ridotto orizzontalmente finché raggiunge questa larghezza.|  
  
## <a name="sizing-rows-and-row-headers"></a>Dimensionamento di righe e le intestazioni di riga  
  
### <a name="datagrid-rows"></a>Righe a DataGrid  
 Per impostazione predefinita, un <xref:System.Windows.Controls.DataGrid> riga <xref:System.Windows.FrameworkElement.Height%2A> è impostata su <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), e l'altezza della riga verrà espanso alle dimensioni del relativo contenuto. L'altezza di tutte le righe di <xref:System.Windows.Controls.DataGrid> può essere specificato impostando il <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> proprietà. Gli utenti possono modificare l'altezza della riga trascinando i separatori di intestazione di riga.  
  
### <a name="datagrid-row-headers"></a>Intestazioni di riga DataGrid  
 Per visualizzare le intestazioni di riga, il <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. Per impostazione predefinita, vengono visualizzate le intestazioni di riga e vengono ridimensionate automaticamente per adattarsi al contenuto. Le intestazioni di riga è possibile assegnare una larghezza specifica impostando la <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="sizing-columns-and-column-headers"></a>Ridimensionamento di colonne e le intestazioni di colonna  
  
### <a name="datagrid-columns"></a>Colonne del DataGrid  
 Il <xref:System.Windows.Controls.DataGrid> utilizza valori del <xref:System.Windows.Controls.DataGridLength> e <xref:System.Windows.Controls.DataGridLengthUnitType> struttura per specificare le modalità di ridimensionamento automatico o assoluto.  
  
 La tabella seguente illustra i valori forniti dal <xref:System.Windows.Controls.DataGridLengthUnitType> struttura.  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Il valore predefinito di dimensioni delle modalità di ridimensionamento automatico <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle celle e intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Il cella automatico dimensioni delle modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle celle della colonna, non includere le intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|L'intestazione automatico dimensioni delle modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle intestazioni di colonna solo.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Basato su pixel le dimensioni di modalità di ridimensionamento <xref:System.Windows.Controls.DataGrid> colonne in base al valore numerico specificato.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|La modalità di ridimensionamento proporzionale viene utilizzata per distribuire lo spazio disponibile in base alle proporzioni ponderate.<br /><br /> In XAML, i valori asterisco sono espressi come n * dove n rappresenta un valore numerico. 1\* equivale a \*. Se, ad esempio, due colonne in un <xref:System.Windows.Controls.DataGrid> dispongono di larghezze di \* e 2\*, la prima colonna riceverebbe una parte dello spazio disponibile e la seconda colonna riceverebbe due parti dello spazio disponibile.|  
  
 Il <xref:System.Windows.Controls.DataGridLengthConverter> classe può essere utilizzata per convertire i dati tra i valori numerici e stringa e <xref:System.Windows.Controls.DataGridLength> valori.  
  
 Per impostazione predefinita, il <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>e <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Quando la modalità di ridimensionamento è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, colonne aumenterà la larghezza del contenuto visibile più ampio. Durante lo scorrimento, queste modalità di ridimensionamento causerà l'espansione se il contenuto delle colonne che è maggiore di quanto la dimensione della colonna corrente è lo scorrimento nella visualizzazione. La colonna non viene compressa dopo il contenuto di fuori della visualizzazione.  
  
 Le colonne di <xref:System.Windows.Controls.DataGrid> può anche essere impostata sul ridimensionamento automatico solo entro limiti specificati, o possono essere impostate su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare le dimensioni delle colonne.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per una singola colonna. Esegue l'override <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per una singola colonna. Esegue l'override <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per tutte le colonne di <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per una singola colonna. Esegue l'override <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Intestazioni delle colonne DataGrid  
 Per impostazione predefinita, <xref:System.Windows.Controls.DataGrid> vengono visualizzate le intestazioni di colonna. Per nascondere le intestazioni di colonna, il <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. Per impostazione predefinita, quando vengono visualizzate le intestazioni di colonna, vengono ridimensionate automaticamente per adattarsi al contenuto. Le intestazioni di colonna è possibile assegnare un'altezza specifica impostando la <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> proprietà.  
  
### <a name="resizing-with-the-mouse"></a>Ridimensionamento con il Mouse  
 Gli utenti possono ridimensionare <xref:System.Windows.Controls.DataGrid> righe e colonne trascinando i separatori di intestazione di riga o colonna. Il <xref:System.Windows.Controls.DataGrid> supporta anche il ridimensionamento automatico di righe e colonne facendo doppio clic sul divisore di intestazione di riga o colonna. Per impedire che un utente il ridimensionamento di colonne specifiche, impostare il <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà `false` per le singole colonne. Per impedire agli utenti di ridimensionare tutte le colonne, impostare il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà `false`. Per impedire agli utenti di ridimensionare tutte le righe, impostare il <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> proprietà `false`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGridColumn>  
 <xref:System.Windows.Controls.DataGridLength>  
 <xref:System.Windows.Controls.DataGridLengthConverter>
