---
title: Opzioni di ridimensionamento nel controllo DataGrid
description: Informazioni su come impostare singole righe e colonne nel controllo DataGrid Windows Presentation Foundation per ridimensionarle al contenuto o a valori specifici.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164749"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Opzioni di ridimensionamento nel controllo DataGrid
Sono disponibili diverse opzioni per controllare la modalità di <xref:System.Windows.Controls.DataGrid> ridimensionamento. <xref:System.Windows.Controls.DataGrid>, E singole righe e colonne in <xref:System.Windows.Controls.DataGrid> , possono essere impostate in modo da ridimensionarle automaticamente al relativo contenuto oppure possono essere impostate su valori specifici. Per impostazione predefinita, <xref:System.Windows.Controls.DataGrid> aumenterà e ridurrà le dimensioni per adattarle al relativo contenuto.  
  
## <a name="sizing-the-datagrid"></a>Ridimensionamento del DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Avvertenze quando si usa il dimensionamento automatico  
 Per impostazione predefinita, <xref:System.Windows.FrameworkElement.Height%2A> le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e di <xref:System.Windows.Controls.DataGrid> sono impostate su <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " in XAML) e l'oggetto <xref:System.Windows.Controls.DataGrid> verrà modificato in base alle dimensioni del contenuto.  
  
 Quando viene inserita all'interno di un contenitore che non limita le dimensioni dei relativi elementi figlio, ad esempio <xref:System.Windows.Controls.Canvas> o <xref:System.Windows.Controls.StackPanel> , la proprietà <xref:System.Windows.Controls.DataGrid> si estenderà oltre i limiti visibili del contenitore e le barre di scorrimento non verranno visualizzate. Questa condizione ha implicazioni sia sull'usabilità che sulle prestazioni.  
  
 Quando viene associato a un set di dati, se l'oggetto <xref:System.Windows.FrameworkElement.Height%2A> di <xref:System.Windows.Controls.DataGrid> non è limitato, continuerà ad aggiungere una riga per ogni elemento di dati del set di dati associato. Questo può causare un <xref:System.Windows.Controls.DataGrid> aumento delle dimensioni all'esterno dei limiti visibili dell'applicazione quando vengono aggiunte righe. <xref:System.Windows.Controls.DataGrid>In questo caso, non visualizzerà le barre di scorrimento perché <xref:System.Windows.FrameworkElement.Height%2A> continuerà ad espandersi per supportare le nuove righe.  
  
 Viene creato un oggetto per ogni riga della <xref:System.Windows.Controls.DataGrid> . Se si utilizza un set di dati di grandi dimensioni e si consente <xref:System.Windows.Controls.DataGrid> a di ridimensionarsi automaticamente, la creazione di un numero elevato di oggetti può influire sulle prestazioni dell'applicazione.  
  
 Per evitare questi problemi quando si lavora con set di dati di grandi dimensioni, è consigliabile impostare in modo specifico il <xref:System.Windows.FrameworkElement.Height%2A> di <xref:System.Windows.Controls.DataGrid> o inserirlo in un contenitore che ne consentirà la limitazione <xref:System.Windows.FrameworkElement.Height%2A> , ad esempio <xref:System.Windows.Controls.Grid> . Quando l'oggetto <xref:System.Windows.FrameworkElement.Height%2A> è limitato, creerà <xref:System.Windows.Controls.DataGrid> solo le righe che rientrano nel relativo oggetto specificato <xref:System.Windows.FrameworkElement.Height%2A> e ricicla tali righe in base alle esigenze per visualizzare i nuovi dati.  
  
### <a name="setting-the-datagrid-size"></a>Impostazione della dimensione DataGrid  
 L'oggetto <xref:System.Windows.Controls.DataGrid> può essere impostato in modo da ridimensionarsi automaticamente entro i limiti specificati oppure <xref:System.Windows.Controls.DataGrid> può essere impostato su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare le <xref:System.Windows.Controls.DataGrid> dimensioni.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Imposta un'altezza specifica per l'oggetto <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Imposta il limite superiore per l'altezza dell'oggetto <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Aumenta verticalmente fino a raggiungere questa altezza.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Imposta il limite inferiore per l'altezza dell'oggetto <xref:System.Windows.Controls.DataGrid> . L'oggetto <xref:System.Windows.Controls.DataGrid> verrà compattato verticalmente fino a quando non raggiunge l'altezza.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Imposta una larghezza specifica per l'oggetto <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Imposta il limite superiore per la larghezza di <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>Aumenta orizzontalmente fino a raggiungere la larghezza.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Imposta il limite inferiore per la larghezza di <xref:System.Windows.Controls.DataGrid> . Si ridurrà <xref:System.Windows.Controls.DataGrid> orizzontalmente fino a quando non raggiunge la larghezza.|  
  
## <a name="sizing-rows-and-row-headers"></a>Ridimensionamento di righe e intestazioni di riga  
  
### <a name="datagrid-rows"></a>DataGrid (righe)  
 Per impostazione predefinita, <xref:System.Windows.Controls.DataGrid> la proprietà di una riga <xref:System.Windows.FrameworkElement.Height%2A> è impostata su <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " in XAML) e l'altezza della riga verrà espansa fino alla dimensione del contenuto. L'altezza di tutte le righe in <xref:System.Windows.Controls.DataGrid> può essere specificata impostando la <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> Proprietà. Gli utenti possono modificare l'altezza della riga trascinando i separatori delle intestazioni di riga.  
  
### <a name="datagrid-row-headers"></a>Intestazioni di riga DataGrid  
 Per visualizzare le intestazioni di riga, la <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> . Per impostazione predefinita, vengono visualizzate le intestazioni di riga e le dimensioni vengono automaticamente adattate al contenuto. Alle intestazioni di riga è possibile assegnare una larghezza specifica impostando la <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> Proprietà.  
  
## <a name="sizing-columns-and-column-headers"></a>Ridimensionamento di colonne e intestazioni di colonna  
  
### <a name="datagrid-columns"></a>Colonne DataGrid  
 <xref:System.Windows.Controls.DataGrid>Usa i valori di <xref:System.Windows.Controls.DataGridLength> e la <xref:System.Windows.Controls.DataGridLengthUnitType> struttura per specificare le modalità di ridimensionamento assoluto o automatico.  
  
 Nella tabella seguente vengono illustrati i valori forniti dalla <xref:System.Windows.Controls.DataGridLengthUnitType> struttura.  
  
|Nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|La modalità di ridimensionamento automatico predefinita ridimensiona le <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle celle e delle intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|La modalità di ridimensionamento automatico basata su celle ridimensiona le <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle celle nella colonna, escluse le intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|La modalità di ridimensionamento automatico basata sull'intestazione ridimensiona le <xref:System.Windows.Controls.DataGrid> colonne in base al contenuto delle intestazioni di colonna.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|La modalità di dimensionamento in base al pixel ridimensiona le <xref:System.Windows.Controls.DataGrid> colonne in base al valore numerico fornito.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|La modalità di ridimensionamento a stella viene utilizzata per distribuire lo spazio disponibile in base alle proporzioni ponderate.<br /><br /> In XAML i valori a stella sono espressi come n * dove n rappresenta un valore numerico. 1 \* equivale a \* . Se, ad esempio, due colonne in un oggetto <xref:System.Windows.Controls.DataGrid> hanno larghezze di \* e 2 \* , la prima colonna riceve una parte dello spazio disponibile e la seconda colonna riceve due parti dello spazio disponibile.|  
  
 La <xref:System.Windows.Controls.DataGridLengthConverter> classe può essere utilizzata per convertire i dati tra valori numerici o di stringa e <xref:System.Windows.Controls.DataGridLength> valori.  
  
 Per impostazione predefinita, la <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> proprietà è impostata su <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> e la <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> proprietà è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A> . Quando la modalità di ridimensionamento è impostata su <xref:System.Windows.Controls.DataGridLength.Auto%2A> o <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> , le colonne aumenteranno fino alla larghezza del contenuto più ampio visibile. Durante lo scorrimento, queste modalità di ridimensionamento comporteranno l'espansione delle colonne se il contenuto maggiore delle dimensioni della colonna corrente viene spostato nella visualizzazione. La colonna non verrà compattata dopo lo scorrimento del contenuto fuori dalla visualizzazione.  
  
 Le colonne in <xref:System.Windows.Controls.DataGrid> possono essere impostate anche per la dimensione automatica solo entro i limiti specificati oppure le colonne possono essere impostate su una dimensione specifica. Nella tabella seguente vengono illustrate le proprietà che è possibile impostare per controllare le dimensioni delle colonne.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per tutte le colonne nell'oggetto <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Imposta il limite superiore per una singola colonna. Esegue l'override dell'oggetto <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per tutte le colonne nell'oggetto <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Imposta il limite inferiore per una singola colonna. Esegue l'override dell'oggetto <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per tutte le colonne nell'oggetto <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Imposta una larghezza specifica per una singola colonna. Esegue l'override dell'oggetto <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>Intestazioni di colonna DataGrid  
 Per impostazione predefinita, <xref:System.Windows.Controls.DataGrid> vengono visualizzate le intestazioni di colonna. Per nascondere le intestazioni di colonna, la <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> proprietà deve essere impostata su <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> o <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> . Per impostazione predefinita, quando vengono visualizzate le intestazioni di colonna, le dimensioni vengono automaticamente adattate al contenuto. Alle intestazioni di colonna può essere assegnata un'altezza specifica impostando la <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> Proprietà.  
  
### <a name="resizing-with-the-mouse"></a>Ridimensionamento con il mouse  
 Gli utenti possono ridimensionare <xref:System.Windows.Controls.DataGrid> righe e colonne trascinando i separatori di intestazioni di riga o di colonna. <xref:System.Windows.Controls.DataGrid>Supporta inoltre il ridimensionamento automatico di righe e colonne facendo doppio clic sul divisore di intestazione di riga o di colonna. Per impedire a un utente di ridimensionare colonne specifiche, impostare la <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà su `false` per le singole colonne. Per impedire agli utenti di ridimensionare tutte le colonne, impostare la <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà su `false` . Per impedire agli utenti di ridimensionare tutte le righe, impostare la <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> proprietà su `false` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
