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
ms.openlocfilehash: 1a79f34daac4238093693947f5fb5e73bb56213d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529025"
---
# <a name="types-of-bitmaps"></a>Tipi di bitmap
Una bitmap è una matrice di bit che specifica il colore di ogni pixel in una matrice rettangolare di pixel. Il numero di bit destinati a un singolo pixel determina il numero di colori che possono essere assegnati a tale pixel. Ad esempio, se ogni pixel è rappresentato da 4 bit, quindi un pixel specifico può essere assegnato uno dei 16 colori diversi (2 ^ 4 = 16). La tabella seguente illustra alcuni esempi del numero di colori che possono essere assegnati a un pixel rappresentato da un determinato numero di bit.  
  
|Bit per pixel|Numero di colori che possono essere assegnati a un pixel|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 File di disco che archiviano le bitmap in genere contengono uno o più blocchi di informazioni che archiviano informazioni quali il numero di bit per pixel, numero di pixel in ogni riga e numero di righe nella matrice. Tale file potrebbe contenere anche una tabella a colori (talvolta denominata una tavolozza dei colori). Una tabella di mappa numeri nella bitmap a colori specifici. Nella figura seguente mostra un'immagine ingrandita con la relativa tabella di bitmap e il colore. Ogni pixel è rappresentato da un numero di 4 bit, pertanto vi sono 2 ^ 4 = 16 colori nella tavolozza colori. Ogni colore nella tabella è rappresentato da un numero di 24 bit: 8 bit del rosso, 8 bit del verde e 8 bit del blu. I numeri vengono visualizzati in formato esadecimale (base 16): A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Esempio di bitmap](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Esaminare il pixel nella riga 3, colonna 5 dell'immagine. Il numero corrispondente nella bitmap è 1. La tabella dei colori indica che 1 rappresenta il colore rosso, pertanto il pixel è rosso. Tutte le voci nella riga superiore della bitmap sono 3. La tabella dei colori indica che 3 rappresenta blue, pertanto tutti i pixel nella parte superiore dell'immagine sono blu.  
  
> [!NOTE]
>  Alcune bitmap vengono archiviate in formato dal basso in alto. i numeri nella prima riga della bitmap corrispondono ai pixel nella riga inferiore dell'immagine.  
  
 Bitmap che archivia gli indici in una tabella dei colori viene chiamata una bitmap con tavolozza indicizzate. Alcune bitmap non sono necessari per una tabella a colori. Ad esempio, se una bitmap Usa 24 bit per pixel, tale bitmap possibile archiviare gli stessi colori piuttosto che gli indici in una tabella a colori. Nella figura seguente mostra una bitmap che vengono archiviati direttamente i colori (24 bit per pixel) anziché una tabella a colori. L'illustrazione mostra anche un ingrandimento dell'immagine corrispondente. Nella mappa di bit, FFFFFF rappresenta il bianco, FF0000 rappresenta il rosso, 00FF00 rappresenta il colore verde e 0000FF rappresenta il blu.  
  
 ![Esempio di bitmap](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Formati di File di grafica  
 Esistono numerosi formati standard per il salvataggio di bitmap nei file su disco. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] supporta la grafica formati di file descritti nei paragrafi seguenti.  
  
### <a name="bmp"></a>BMP  
 BMP è un formato standard utilizzato da Windows per archiviare le immagini indipendenti dal dispositivo e indipendenti dall'applicazione. Il numero di bit per pixel (1, 4, 8, 15, 24, 32 o 64) per un determinato file BMP è specificato in un'intestazione del file. I file BMP con 24 bit per pixel sono comuni. File BMP in genere non vengono compressi e, pertanto, non sono adatti per il trasferimento tramite Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Graphics Interchange Format (GIF)  
 GIF è un formato comune per le immagini visualizzate nelle pagine Web. GIF funziona anche per le linee, le immagini con blocchi di colore a tinta unita e immagini con limiti acuti tra i colori. GIF sono compresse, senza alcuna perdita di informazioni nel processo di compressione; un'immagine decompressa è esattamente uguale all'originale. È possibile impostare un colore di un'immagine GIF trasparente, in modo che l'immagine assumerà il colore di sfondo di una pagina Web che viene visualizzato. Una sequenza di immagini GIF può essere archiviata in un singolo file in modo da formare un'immagine GIF animata. GIF archiviare al massimo 8 bit per pixel, in modo che sono limitati a 256 colori.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG è uno schema di compressione che funziona anche per le scene naturale, ad esempio acquisite. Alcune informazioni vengono persi nel processo di compressione, ma spesso la perdita è impercettibile all'occhio umano. File JPEG memorizzare 24 bit per pixel, in modo che siano in grado di visualizzare più di 16 milioni di colori. File JPEG non supportano la trasparenza o animazione.  
  
 Il livello di compressione immagini JPEG è configurabile, ma i livelli più alti di compressione (i file più piccoli) ottenere maggiore perdita di informazioni. Spesso, un rapporto di compressione di 20:1 produce un'immagine che all'occhio umano ma consente di trovare facilmente distinguibili dai originale. Nella figura seguente mostra un'immagine BMP e due le immagini JPEG che sono stati compressi da quell'immagine BMP. La prima immagine JPEG un rapporto di compressione di 4:1, che la seconda immagine JPEG ha un rapporto di compressione di circa 8:1.  
  
 ![Esempi di FileType](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 La compressione JPEG non funzionerà correttamente per le linee, blocchi di colore a tinta unita e acuto limiti. Nella figura seguente mostra un'immagine BMP con due immagini JPEG e un'immagine GIF. Le immagini JPEG e GIF sono stati compressi dal BMP. Il rapporto di compressione è 4:1 per l'immagine GIF, 4:1 per il più piccolo JPEG e 8:3 per l'immagine JPEG più grande. Si noti che il file GIF mantiene i limiti acuti lungo le righe, ma le immagini JPEG tendono a sfumati.  
  
 ![I tipi di file](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG è uno schema di compressione non è un formato di file. File JFIF JPEG Interchange Format () è un formato di file utilizzato per l'archiviazione e il trasferimento di immagini che sono state compresse in base allo schema JPEG. I file JFIF visualizzati dai browser Web utilizzano l'estensione jpg.  
  
### <a name="exchangeable-image-file-exif"></a>Exchangeable Image File (EXIF)  
 EXIF è un formato di file utilizzato per immagini acquisite da fotocamere digitali. Un file EXIF contiene un'immagine che viene compresso in base alla specifica JPEG. Un file EXIF contiene inoltre informazioni relative alla fotografia (data di acquisizione, otturatore velocità, il tempo di esposizione e così via) e le informazioni relative alla fotocamera (produttore, modello e così via).  
  
### <a name="portable-network-graphics-png"></a>Portable Network Graphics (PNG)  
 Il formato PNG mantiene molti dei vantaggi del formato GIF, ma fornisce anche funzionalità oltre a quelle di immagine GIF. Analogamente ai file GIF, PNG sono compressi senza perdita di informazioni. File PNG è possono archiviare i colori con 8, 24, o 48 bit per pixel e scale di grigi con 1, 2, 4, 8 o 16 bit per pixel. GIF (file), invece, possono utilizzare solo 1, 2, 4 o 8 bit per pixel. Un file PNG è anche possibile archiviare un valore alfa per ciascun pixel, che specifica il livello a cui il colore del pixel viene sfumato con il colore di sfondo.  
  
 PNG migliora la possibilità di visualizzare progressivamente un'immagine GIF (ovvero, per visualizzare approssimazioni sempre migliori dell'immagine come arriva tramite una connessione di rete). File PNG possono contenere informazioni di correzione di colore e la correzione gamma in modo che sia possono eseguire il rendering in modo accurato di immagini su una vasta gamma di dispositivi di visualizzazione.  
  
### <a name="tag-image-file-format-tiff"></a>Tag immagine formato TIFF (File)  
 TIFF è un formato flessibile ed estendibile che è supportato da una vasta gamma di piattaforme e applicazioni di elaborazione delle immagini. File TIFF possono archiviare le immagini con un numero arbitrario di bit per pixel e possono utilizzare un'ampia gamma di algoritmi di compressione. Numerose immagini possono essere archiviate in un file TIFF singolo a più pagine. Le informazioni relative all'immagine (marca dello scanner, il computer host, tipo di compressione, orientamento, i campioni per pixel e così via) possono essere archiviate nel file e disposti tramite l'utilizzo di tag. Il formato TIFF può essere esteso in base alle esigenze di approvazione e l'aggiunta di nuovi tag.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <xref:System.Drawing.Bitmap?displayProperty=nameWithType>  
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
