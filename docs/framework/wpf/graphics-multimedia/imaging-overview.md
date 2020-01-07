---
title: Cenni preliminari sulla creazione dell'immagine
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: a4151ff610c67ac762f0096c6a136f4475317782
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636640"
---
# <a name="imaging-overview"></a>Cenni preliminari sulla creazione dell'immagine
In questo argomento viene fornita un'introduzione al componente Microsoft Windows Presentation Foundation Imaging. La creazione di immagini WPF consente agli sviluppatori di visualizzare, trasformare e formattare le immagini.  

## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 La creazione di immagini WPF offre miglioramenti significativi nelle funzionalità di creazione di immagini in Microsoft Windows. Le funzionalità di creazione di immagini, ad esempio la visualizzazione di una bitmap o l'uso di un'immagine in un controllo comune, dipendono in precedenza dalle librerie Microsoft Windows Graphics Device Interface (GDI) o GDI+ di Microsoft Windows. Queste API offrono funzionalità di imaging di base, ma non dispongono di funzionalità come il supporto per l'estendibilità dei codec e il supporto per immagini ad alta fedeltà. La creazione di immagini WPF è progettata per superare le carenze di GDI e GDI+ e offrire un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Esistono due modi per accedere all'API di imaging WPF, a un componente gestito e a un componente non gestito. Il componente non gestito fornisce le funzionalità riportate di seguito.  
  
- Modello di estendibilità per formati di immagine nuovi o proprietari.  
  
- Miglioramento delle prestazioni e della sicurezza dei formati di immagine nativi, tra cui bitmap (BMP), gruppo di esperti di fotografica (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), e icona (. ico).  
  
- Conservazione dei dati di immagini con intensità fino a 8 bit per canale (32 bit per pixel).  
  
- Ridimensionamento, ritaglio e rotazione delle immagini non distruttivi.  
  
- Gestione dei colori semplificata.  
  
- Supporto per i metadati proprietari all'interno dei file.  
  
- Il componente gestito utilizza l'infrastruttura non gestita per offrire una facile integrazione delle immagini con altre funzionalità di WPF, ad esempio [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animazione e grafica. Il componente gestito trae anche vantaggio dal modello di estendibilità del codec di imaging Windows Presentation Foundation (WPF), che consente il riconoscimento automatico dei nuovi formati di immagini nelle applicazioni WPF.  
  
 La maggior parte dell'API per la creazione di immagini WPF gestita risiede nello spazio dei nomi <xref:System.Windows.Media.Imaging?displayProperty=nameWithType>, anche se diversi tipi importanti, ad esempio <xref:System.Windows.Media.ImageBrush> e <xref:System.Windows.Media.ImageDrawing> risiedono nello spazio dei nomi <xref:System.Windows.Media?displayProperty=nameWithType> e <xref:System.Windows.Controls.Image> si trovano nello spazio dei nomi <xref:System.Windows.Controls?displayProperty=nameWithType>.  
  
 Questo argomento include informazioni aggiuntive sul componente gestito. Per ulteriori informazioni sull'API non gestita, vedere la documentazione relativa ai componenti per la [creazione di immagini WPF non gestite](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formati di immagini WPF  

 Viene usato un codec per decodificare o codificare un formato multimediale specifico. La creazione di immagini WPF include un codec per i formati di immagine BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF e ICON. Ognuno di questi codec consente alle applicazioni di decodificare e, ad eccezione di ICON, codificare i rispettivi formati di immagine.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> è una classe importante utilizzata per la decodifica e la codifica delle immagini. Si tratta del blocco predefinito di base della pipeline di imaging WPF e rappresenta un singolo set costante di pixel a una determinata dimensione e risoluzione. Un <xref:System.Windows.Media.Imaging.BitmapSource> può essere un singolo frame di un'immagine a più frame oppure il risultato di una trasformazione eseguita su una <xref:System.Windows.Media.Imaging.BitmapSource>. È l'elemento padre di molte delle classi primarie utilizzate nella creazione di immagini WPF, ad esempio <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Viene utilizzato un <xref:System.Windows.Media.Imaging.BitmapFrame> per archiviare i dati bitmap effettivi di un formato di immagine. Molti formati di immagine supportano solo una singola <xref:System.Windows.Media.Imaging.BitmapFrame>, anche se formati quali GIF e TIFF supportano più frame per ogni immagine. I fotogrammi vengono usati dai decodificatori come dati di input e vengono passati ai codificatori per creare file di immagine.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Media.Imaging.BitmapFrame> da un <xref:System.Windows.Media.Imaging.BitmapSource> e quindi aggiungerlo a un'immagine TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Decodifica dei formati di immagine  
 La decodifica delle immagini è la conversione di un formato di immagine in dati di immagine che possono essere usati dal sistema. I dati dell'immagine possono quindi essere usati per visualizzare, elaborare o eseguire la codifica in un formato diverso. La scelta del decodificatore varia a seconda del formato di immagine. La selezione del codec è automatica, a meno che non si indichi un decodificatore specifico. Gli esempi nella sezione [Visualizzazione di immagini in WPF](#_displayingimages) illustrano la decodifica automatica. I decodificatori di formato personalizzati sviluppati utilizzando le interfacce di imaging WPF non gestite e registrati con il sistema partecipano automaticamente alla selezione del decodificatore. In questo modo è possibile visualizzare automaticamente i formati personalizzati nelle applicazioni WPF.  
  
 Nell'esempio seguente viene illustrato l'utilizzo di un decodificatore bitmap per decodificare un'immagine in formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codifica dei formati di immagine  
 La codifica delle immagini è la conversione di dati di immagine in un formato di immagine specifico. I dati di immagine codificati possono quindi essere usati per creare nuovi file di immagine. La creazione di immagini WPF fornisce codificatori per ognuno dei formati di immagine descritti in precedenza.  
  
 L'esempio seguente illustra l'uso di un codificatore per salvare un'immagine bitmap appena creata.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Visualizzazione di immagini in WPF  
 Esistono diversi modi per visualizzare un'immagine in un'applicazione Windows Presentation Foundation (WPF). Le immagini possono essere visualizzate utilizzando un controllo <xref:System.Windows.Controls.Image>, dipinte su un oggetto visivo utilizzando una <xref:System.Windows.Media.ImageBrush>o disegnate utilizzando un <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Uso del controllo Image  
 <xref:System.Windows.Controls.Image> è un elemento del Framework e il modo principale per visualizzare le immagini nelle applicazioni. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<xref:System.Windows.Controls.Image> può essere utilizzato in due modi: sintassi degli attributi o sintassi della proprietà. L'esempio seguente mostra come eseguire il rendering di un'immagine con una larghezza di 200 pixel mediante la sintassi di attributo e la sintassi di tag di proprietà. Per altre informazioni sulla sintassi degli attributi e la sintassi di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Molti esempi usano un oggetto <xref:System.Windows.Media.Imaging.BitmapImage> per fare riferimento a un file di immagine. <xref:System.Windows.Media.Imaging.BitmapImage> è un <xref:System.Windows.Media.Imaging.BitmapSource> specializzato ottimizzato per il caricamento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ed è un modo semplice per visualizzare le immagini come <xref:System.Windows.Controls.Image.Source%2A> di un controllo <xref:System.Windows.Controls.Image>.  
  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage> implementa l'interfaccia <xref:System.ComponentModel.ISupportInitialize> per ottimizzare l'inizializzazione su più proprietà. Le proprietà possono essere modificate solo durante l'inizializzazione degli oggetti. Chiamare <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> per segnalare che l'inizializzazione è iniziata e <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> per segnalare che l'inizializzazione è stata completata. Dopo aver eseguito l'inizializzazione, le modifiche alle proprietà verranno ignorate.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Rotazione, conversione e ritaglio di immagini  
 WPF consente agli utenti di trasformare le immagini usando le proprietà di <xref:System.Windows.Media.Imaging.BitmapImage> o usando oggetti <xref:System.Windows.Media.Imaging.BitmapSource> aggiuntivi, ad esempio <xref:System.Windows.Media.Imaging.CroppedBitmap> o <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Queste trasformazioni di immagini possono ridimensionare, ruotare, modificare il formato dei pixel o ritagliare un'immagine.  
  
 Le rotazioni delle immagini vengono eseguite utilizzando la proprietà <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> di <xref:System.Windows.Media.Imaging.BitmapImage>. Le rotazioni possono essere eseguite solo in incrementi di 90 gradi. Nell'esempio seguente un'immagine viene ruotata di 90 gradi.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversione di un'immagine in un formato pixel diverso, ad esempio le gradazioni di grigio, viene eseguita utilizzando <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Negli esempi seguenti un'immagine viene convertita in <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Per ritagliare un'immagine, è possibile usare la proprietà <xref:System.Windows.UIElement.Clip%2A> di <xref:System.Windows.Controls.Image> o <xref:System.Windows.Media.Imaging.CroppedBitmap>. In genere, se si vuole solo visualizzare una parte di un'immagine, è necessario usare <xref:System.Windows.UIElement.Clip%2A>. Se è necessario codificare e salvare un'immagine ritagliata, è necessario utilizzare il <xref:System.Windows.Media.Imaging.CroppedBitmap>. Nell'esempio seguente un'immagine viene ritagliata utilizzando la proprietà clip utilizzando un <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Adattamento delle immagini  
 La proprietà <xref:System.Windows.Controls.Image.Stretch%2A> controlla il modo in cui un'immagine viene allungata per riempire il relativo contenitore. La proprietà <xref:System.Windows.Controls.Image.Stretch%2A> accetta i valori seguenti, definiti dall'enumerazione <xref:System.Windows.Media.Stretch>:  
  
- <xref:System.Windows.Media.Stretch.None>: l'immagine non viene adattata per riempire l'area di output. Se l'immagine è più grande dell'area di output, viene disegnata al suo interno, escludendo gli elementi in eccesso.  
  
- <xref:System.Windows.Media.Stretch.Fill>: l'immagine viene ridimensionata in base all'area di output. Poiché l'altezza e la larghezza dell'immagine vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali dell'immagine. In altre parole, l'immagine potrebbe essere distorta per adattarsi completamente al contenitore dell'output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: l'immagine viene ridimensionata in modo da adattarla completamente all'area di output. Vengono mantenute le proporzioni dell'immagine.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: l'immagine viene ridimensionata in modo da riempire completamente l'area di output mantenendo le proporzioni originali dell'immagine.  
  
 Nell'esempio seguente viene applicata ogni enumerazione <xref:System.Windows.Media.Stretch> disponibile a una <xref:System.Windows.Controls.Image>.  
  
 La figura seguente mostra l'output dell'esempio e illustra l'effetto delle diverse impostazioni di <xref:System.Windows.Controls.Image.Stretch%2A> quando vengono applicate a un'immagine.  
  
 ![TileBrush con impostazioni Stretch diverse](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Impostazioni Stretch diverse  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Disegnare con immagini  
 Le immagini possono essere visualizzate anche in un'applicazione disegnando con un <xref:System.Windows.Media.Brush>. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini. Per disegnare con immagini, usare un <xref:System.Windows.Media.ImageBrush>. Un <xref:System.Windows.Media.ImageBrush> è un tipo di <xref:System.Windows.Media.TileBrush> che ne definisce il contenuto come immagine bitmap. Un <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine, specificata dalla relativa proprietà <xref:System.Windows.Media.ImageBrush.ImageSource%2A>. È possibile controllare il modo in cui l'immagine viene adattata, allineata e affiancata, consentendo di evitare distorsioni e produrre motivi e altri effetti. Nella figura seguente vengono illustrati alcuni effetti che è possibile ottenere con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Esempi di output di ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
I pennelli immagine possono riempire forme, controlli, testo e altro ancora  
  
 Nell'esempio seguente viene illustrato come disegnare lo sfondo di un pulsante con un'immagine utilizzando un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Per ulteriori informazioni sulle immagini di <xref:System.Windows.Media.ImageBrush> e disegno, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadati delle immagini  
 Alcuni file di immagine contengono metadati che descrivono il contenuto o le caratteristiche del file. La maggior parte delle fotocamere digitali, ad esempio, crea immagini che contengono i metadati relativi a marca e modello della fotocamera usata per acquisire l'immagine. Ogni formato di immagine gestisce i metadati in modo diverso, ma la creazione di immagini WPF fornisce un modo uniforme per archiviare e recuperare i metadati per ogni formato di immagine supportato.  
  
 L'accesso ai metadati viene fornito tramite la proprietà <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> di un oggetto <xref:System.Windows.Media.Imaging.BitmapSource>. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> restituisce un oggetto <xref:System.Windows.Media.Imaging.BitmapMetadata> che include tutti i metadati contenuti nell'immagine. Questi dati possono essere in uno schema di metadati o in una combinazione di schemi diversi. La creazione di immagini WPF supporta gli schemi di metadati delle immagini seguenti: file di immagine scambiabile (EXIF), testo (dati testuali PNG), directory file di immagine (IFD), International Press Telecommunications Council (IPTC) ed Extensible Metadata Platform (XMP).  
  
 Per semplificare il processo di lettura dei metadati, <xref:System.Windows.Media.Imaging.BitmapMetadata> fornisce diverse proprietà denominate a cui è possibile accedere facilmente, ad esempio <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>e <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Molte di queste proprietà denominate consentono anche di scrivere metadati. Il lettore di query dei metadati fornisce supporto aggiuntivo per la lettura dei metadati. Il metodo <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> viene utilizzato per recuperare un lettore di query di metadati fornendo una query di tipo stringa, ad esempio *"/app1/exif/"* . Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> viene usato per ottenere il testo archiviato nel percorso *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Per scrivere i metadati viene usato il relativo writer di query. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> ottiene il writer di query e imposta il valore desiderato. Nell'esempio seguente <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> viene usato per scrivere il testo archiviato nel percorso *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Estendibilità dei codec  
 Una funzionalità di base dell'imaging WPF è il modello di estendibilità per i nuovi codec di immagine. Queste interfacce non gestite consentono agli sviluppatori di codec di integrare i codec con WPF, in modo che le applicazioni WPF possano usare automaticamente nuovi formati di immagine.  
  
 Per un esempio di API di estendibilità, vedere il [codec di esempio Win32](https://go.microsoft.com/fwlink/?LinkID=160052). Questo esempio spiega come creare un decodificatore e un codificatore per un formato di immagine personalizzato.  
  
> [!NOTE]
> Il codec deve essere firmato digitalmente per il sistema affinché venga riconosciuto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Codec di esempio di Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
