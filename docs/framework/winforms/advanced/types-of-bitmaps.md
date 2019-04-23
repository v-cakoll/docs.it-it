---
title: Tipi di bitmap
ms.date: 03/30/2017
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
ms.openlocfilehash: f41585ba8816e0b1894a9f01163191848ae391e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089170"
---
# <a name="types-of-bitmaps"></a>Tipi di bitmap
Una bitmap è una matrice di bit che specifica il colore di ogni pixel in una matrice rettangolare di pixel. Il numero di bit destinati a un singolo pixel determina il numero di colori che possono essere assegnati a tale pixel. Ad esempio, se ogni pixel è rappresentato da 4 bit, quindi un pixel specifico può essere assegnato uno dei 16 colori diversi (2 ^ 4 = 16). Nella tabella seguente vengono illustrati alcuni esempi del numero di colori che possono essere assegnati a un pixel rappresentato da un determinato numero di bit.  
  
|Bit per pixel|Numero di colori che possono essere assegnati a un pixel|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 I file di disco che archiviano le bitmap in genere contengono uno o più blocchi di informazioni che archiviano informazioni quali il numero di bit per pixel, numero di pixel in ogni riga e numero di righe nella matrice. Questo file potrebbe contenere anche una tabella di colore (operazione talvolta denominata una tavolozza dei colori). Una tabella dei colori mappa numeri nella bitmap a colori specifici. La figura seguente mostra un'immagine ingrandita insieme alla relativa tabella di mappa di bit e il colore. Ogni pixel è rappresentato da un numero di bit 4, pertanto vi sono 2 ^ 4 = 16 colori nella tabella dei colori. Ogni colore nella tabella è rappresentato da un numero di 24 bit: 8 bit per il rosso, 8 bit per il verde e 8 bit per il blu. I numeri vengono visualizzati in formato esadecimale (base 16): A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Bitmap sample](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Esaminare il pixel nella riga 3 della colonna 5 dell'immagine. Il numero corrispondente nella bitmap è 1. La tabella dei colori indica che 1 rappresenta il colore rosso in modo che il pixel è rosso. Tutte le voci di riga superiore della mappa di bit sono 3. La tabella dei colori per indicare che 3 rappresenta il blu, in modo che tutti i pixel nella riga superiore dell'immagine sono blu.  
  
> [!NOTE]
>  Abbiamo delle bitmap viene archiviate in formato dal basso in alto. i numeri nella prima riga della bitmap corrispondono ai pixel nella riga inferiore dell'immagine.  
  
 Bitmap che archivia gli indici in una tabella dei colori viene chiamata una bitmap con tavolozza-indicizzate. Abbiamo delle bitmap non necessario per una tabella dei colori. Ad esempio, se una bitmap Usa 24 bit per pixel, quella bitmap può archiviare gli stessi colori anziché gli indici in una tabella dei colori. La figura seguente mostra una bitmap che archivia direttamente i colori (24 bit per pixel) invece di usare una tabella dei colori. L'illustrazione mostra anche un ingrandimento dell'immagine corrispondente. Nella mappa di bit, FFFFFF rappresenta white FF0000 rappresenta il rosso, 00FF00 rappresenta il colore verde e 0000FF rappresenta blu.  
  
 ![Bitmap sample](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Formati di File grafici  
 Esistono numerosi formati standard per il salvataggio di bitmap in file di disco. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] supporta i file grafici formati descritti nei paragrafi seguenti.  
  
### <a name="bmp"></a>BMP  
 BMP è un formato standard usato da Windows per archiviare immagini indipendenti dal dispositivo e indipendente dalle applicazioni. Il numero di bit per pixel (1, 4, 8, 15, 24, 32 o 64) per un determinato file con estensione BMP viene specificato in un'intestazione del file. File BMP con 24 bit per pixel sono comuni. File BMP in genere non vengono compressi e, pertanto, non sono adatti per il trasferimento tramite Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Graphics Interchange Format (GIF)  
 GIF è un formato comune per le immagini visualizzate nelle pagine Web. GIF funziona bene per le linee, immagini con blocchi di colore a tinta unita e immagini con limiti ben strutturati tra i colori. Vengono compresse immagini GIF animate, ma nessuna informazione viene perso durante il processo di compressione. un'immagine decompressa è esattamente identico all'originale. Un colore in formato GIF può essere designato come trasparente, in modo che l'immagine presenterà il colore di sfondo di qualsiasi pagina Web che li visualizza. Una sequenza di immagini GIF può essere archiviata in un singolo file in modo da formare un GIF animato. GIF archiviare al massimo 8 bit per pixel, in modo che siano limitati a 256 colori.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 Il formato JPEG è uno schema di compressione che funziona bene per le scene naturale, ad esempio acquisite. Alcune informazioni vengono perse nel processo di compressione, ma spesso la perdita è impercettibile all'occhio umano. File JPEG archiviare 24 bit per pixel, in modo che siano in grado di visualizzare più di 16 milioni di colori. File JPEG non supportano la trasparenza o animazioni.  
  
 Il livello di compressione di immagini JPEG è configurabile, ma i livelli di compressione superiori (file più piccoli) causa la perdita più informazioni. Spesso, un rapporto di 20:1 compressione produce un'immagine che occhio umano ma consente di trovare facilmente distinguibili dai originale. La figura seguente mostra un'immagine BMP e due immagini JPEG che sono stati compressi da tale immagine BMP. La prima immagine JPEG è un rapporto di compressione di 4:1 e la seconda immagine JPEG è un rapporto di compressione di 8:1 circa.  
  
 ![Esempi di FileType](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 Compressione JPEG non funziona anche per disegni di riga, i blocchi di colore a tinta unita e ben strutturata dei limiti. La figura seguente mostra un'immagine BMP con due immagini JPEG e GIF. Le immagini JPEG e GIF sono stati compressi dal BMP. Il rapporto di compressione è 4:1 per il GIF, 4:1 per il più piccolo JPEG e 8:3 per JPEG di dimensioni maggiori. Si noti che il GIF mantiene i limiti sharp lungo le righe, ma le immagini JPEG tendono a sfocare i limiti.  
  
 ![Filetypes](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 Il formato JPEG è uno schema di compressione, non un formato di file. File JFIF JPEG Interchange Format () è un formato file comunemente usato per l'archiviazione e trasferimento di immagini che sono state compresse secondo schema JPEG. File JFIF visualizzati dai Web browser usano l'estensione jpg.  
  
### <a name="exchangeable-image-file-exif"></a>Exchangeable Image File (EXIF)  
 EXIF è un formato di file utilizzato per immagini acquisite da fotocamere digitali. Un file EXIF contiene un'immagine compressa in base alle specifiche JPEG. Un file EXIF contiene anche informazioni relative alla fotografia (data di acquisizione, otturatore velocità, il tempo di esposizione e così via) e le informazioni relative alla fotocamera (produttore, modello e così via).  
  
### <a name="portable-network-graphics-png"></a>Portable Network Graphics (PNG)  
 Il formato PNG mantiene molti dei vantaggi del formato GIF ma fornisce anche funzionalità oltre a quelle di immagine GIF. Analogamente ai file GIF, PNG sono compressi senza alcuna perdita di informazioni. File PNG possono archiviare i colori con 8, 24, o 48 bit per pixel e scale di grigi con 1, 2, 4, 8 o 16 bit per pixel. File GIF, invece, possono usare solo 1, 2, 4 o 8 bit per pixel. Un file PNG è anche possibile archiviare un valore alfa per ciascun pixel, che specifica il livello a cui il colore di tale pixel viene sfumato con il colore di sfondo.  
  
 PNG migliora la possibilità di progressivamente visualizzare un'immagine GIF (vale a dire, per visualizzare sempre migliori approssimazioni dell'immagine che arriva tramite una connessione di rete). File PNG possono contenere informazioni di correzione gamma correzione e il colore in modo che sia possono eseguire il rendering in modo accurato di immagini in un'ampia gamma di dispositivi di visualizzazione.  
  
### <a name="tag-image-file-format-tiff"></a>Formato di File di tag immagine (TIFF)  
 TIFF è un formato flessibile ed estendibile che è supportato da un'ampia gamma di piattaforme e applicazioni di elaborazione di immagini. File TIFF consente di archiviare immagini con un numero arbitrario di bit per pixel e possono usare un'ampia gamma di algoritmi di compressione. Numerose immagini possono essere archiviate in un file TIFF singolo a più pagine. Informazioni correlate all'immagine (scanner marca, il computer host, tipo di compressione, orientamento, gli esempi per ogni pixel e così via) possono essere archiviate nel file e disposti tramite l'uso di tag. Il formato TIFF può essere esteso in base alle necessità per l'approvazione e l'aggiunta di nuovi tag.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
