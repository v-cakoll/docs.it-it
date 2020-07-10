---
title: Tipi di bitmap
description: Informazioni sui tipi di bitmap e i formati di file grafici GDI+ supportati, tra cui BMP, JPG, GIF, PNG e TIFF.
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
ms.openlocfilehash: 09b74ef476467b0bba5aac1f58db278b3898ef17
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174679"
---
# <a name="types-of-bitmaps"></a>Tipi di bitmap
Una bitmap è una matrice di bit che specificano il colore di ogni pixel in una matrice rettangolare di pixel. Il numero di bit dedicati a un singolo pixel determina il numero di colori che è possibile assegnare al pixel. Se, ad esempio, ogni pixel è rappresentato da 4 bit, a un determinato pixel può essere assegnato uno dei 16 colori diversi (2 ^ 4 = 16). Nella tabella seguente vengono illustrati alcuni esempi del numero di colori che possono essere assegnati a un pixel rappresentato da un numero specificato di bit.  
  
|Bit per pixel|Numero di colori che possono essere assegnati a un pixel|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 I file su disco in cui sono archiviate le bitmap contengono in genere uno o più blocchi di informazioni che archiviano informazioni quali il numero di bit per pixel, il numero di pixel in ogni riga e il numero di righe nella matrice. Tale file potrebbe inoltre contenere una tabella dei colori (talvolta denominata tavolozza dei colori). Una tabella dei colori esegue il mapping dei numeri nella bitmap a colori specifici. Nella figura seguente viene illustrata un'immagine ingrandita insieme alla relativa bitmap e tabella dei colori. Ogni pixel è rappresentato da un numero a 4 bit, quindi sono presenti 2 ^ 4 = 16 colori nella tabella dei colori. Ogni colore della tabella è rappresentato da un numero a 24 bit: 8 bit per il rosso, 8 bit per il verde e 8 bit per il blu. I numeri sono visualizzati in formato esadecimale (base 16): A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Esempio di bitmap](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Osservare il pixel nella riga 3, colonna 5 dell'immagine. Il numero corrispondente nella bitmap è 1. La tabella dei colori indica che 1 rappresenta il colore rosso, in modo che il pixel sia rosso. Tutte le voci nella prima riga della bitmap sono 3. La tabella dei colori indica che 3 rappresenta il blu, quindi tutti i pixel nella riga superiore dell'immagine sono blu.  
  
> [!NOTE]
> Alcune bitmap sono archiviate in formato bottom-up; i numeri nella prima riga della bitmap corrispondono ai pixel nella riga inferiore dell'immagine.  
  
 Una bitmap che archivia gli indici in una tabella dei colori è detta bitmap indicizzata dalla tavolozza. Alcune bitmap non hanno bisogno di una tabella dei colori. Se, ad esempio, una bitmap utilizza 24 bit per pixel, tale bitmap può archiviare i colori stessi anziché gli indici in una tabella dei colori. Nella figura seguente viene illustrata una bitmap che archivia direttamente i colori (24 bit per pixel) anziché utilizzare una tabella dei colori. L'illustrazione mostra anche una visualizzazione ingrandita dell'immagine corrispondente. Nella bitmap FFFFFF rappresenta il bianco, FF0000 rappresenta il rosso, 00FF00 rappresenta il verde e 0000FF rappresenta il blu.  
  
 ![Esempio di bitmap](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Formati di file di grafica  
 Sono disponibili molti formati standard per il salvataggio di bitmap nei file su disco. GDI+ supporta i formati di file di grafica descritti nei paragrafi seguenti.  
  
### <a name="bmp"></a>BMP  
 BMP è un formato standard usato da Windows per archiviare le immagini indipendenti dal dispositivo e dalle applicazioni. Il numero di bit per pixel (1, 4, 8, 15, 24, 32 o 64) per un determinato file BMP è specificato in un'intestazione di file. I file BMP con 24 bit per pixel sono comuni. I file BMP non sono in genere compressi e, pertanto, non sono particolarmente adatti per il trasferimento in Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Graphics Interchange Format (GIF)  
 GIF è un formato comune per le immagini visualizzate nelle pagine Web. Le gif sono ideali per i disegni di linee, le immagini con blocchi di colore a tinta unita e le immagini con limiti acuti tra i colori. Le gif sono compresse, ma le informazioni non vengono perse nel processo di compressione. un'immagine decompressa è esattamente identica a quella originale. Un colore in un GIF può essere designato come trasparente, in modo che l'immagine abbia il colore di sfondo di tutte le pagine Web che lo visualizzano. Una sequenza di immagini GIF può essere archiviata in un singolo file per formare un GIF animato. Gif archivia al massimo 8 bit per pixel, quindi sono limitati a 256 colori.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG è uno schema di compressione che funziona bene per le scene naturali, ad esempio le fotografie sottoposte a scansione. Alcune informazioni vengono perse nel processo di compressione, ma spesso la perdita è impercettibile all'occhio umano. I file JPEG archiviano 24 bit per pixel, quindi sono in grado di visualizzare più di 16 milioni colori. I file JPEG non supportano la trasparenza o l'animazione.  
  
 Il livello di compressione nelle immagini JPEG è configurabile, ma i livelli di compressione più elevati (file più piccoli) generano una perdita di informazioni maggiore. Un rapporto di compressione 20:1 produce spesso un'immagine che l'occhio umano trova difficile distinguere dall'originale. La figura seguente mostra un'immagine BMP e due immagini JPEG che sono state compresse da tale immagine BMP. Il primo file JPEG ha un rapporto di compressione di 4:1 e il secondo formato JPEG ha un rapporto di compressione di circa 8:1.  
  
 ![Esempi di Filetype](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 La compressione JPEG non funziona bene per i disegni di linee, i blocchi di colore a tinta unita e i limiti acuti. Nella figura seguente viene illustrata una BMP insieme a due file JPEG e un file GIF. I file JPEG e GIF sono stati compressi da BMP. Il rapporto di compressione è 4:1 per GIF, 4:1 per il formato JPEG più piccolo e 8:3 per il file JPEG più grande. Si noti che il file GIF mantiene i limiti acuti lungo le righe, ma i file JPEG tendono a sfocare i limiti.  
  
 ![Filetype](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG è uno schema di compressione, non un formato di file. JPEG File Interchange Format (JFIF) è un formato di file comunemente usato per l'archiviazione e il trasferimento di immagini che sono state compresse in base allo schema JPEG. I file JFIF visualizzati dai Web browser usano l'estensione jpg.  
  
### <a name="exchangeable-image-file-exif"></a>File di immagine scambiabile (EXIF)  
 EXIF è un formato di file usato per le fotografie acquisite dalle fotocamere digitali. Un file EXIF contiene un'immagine compressa in base alla specifica JPEG. Un file EXIF contiene anche informazioni sulla fotografia (data di scadenza, velocità dell'otturatore, tempo di esposizione e così via) e informazioni sulla fotocamera (produttore, modello e così via).  
  
### <a name="portable-network-graphics-png"></a>Portable Network Graphics (PNG)  
 Il formato PNG mantiene molti dei vantaggi del formato GIF, ma offre anche funzionalità oltre a quelle di GIF. Analogamente ai file GIF, i file PNG vengono compressi senza perdita di informazioni. I file PNG possono archiviare colori con 8, 24 o 48 bit per pixel e scala di grigi con 1, 2, 4, 8 o 16 bit per pixel. Al contrario, i file GIF possono utilizzare solo 1, 2, 4 o 8 bit per pixel. Un file PNG può inoltre archiviare un valore alfa per ogni pixel, che specifica il grado di fusione del colore del pixel con il colore di sfondo.  
  
 Il formato PNG migliora il GIF con la possibilità di visualizzare progressivamente un'immagine, ovvero di visualizzare approssimazioni migliori e migliori dell'immagine Man mano che arriva attraverso una connessione di rete. I file PNG possono contenere informazioni sulla correzione gamma e sulla correzione dei colori, in modo che sia possibile eseguire il rendering accurato delle immagini in un'ampia gamma di dispositivi di visualizzazione.  
  
### <a name="tag-image-file-format-tiff"></a>Formato TIFF (Tag Image File Format)  
 TIFF è un formato flessibile ed estendibile supportato da un'ampia gamma di piattaforme e applicazioni per l'elaborazione di immagini. I file TIFF possono archiviare immagini con un numero arbitrario di bit per pixel e possono utilizzare diversi algoritmi di compressione. Diverse immagini possono essere archiviate in un singolo file TIFF a più pagine. Le informazioni relative all'immagine, ovvero la marca dello scanner, il computer host, il tipo di compressione, l'orientamento, gli esempi per pixel e così via, possono essere archiviate nel file e disposte attraverso l'uso dei tag. Il formato TIFF può essere esteso come richiesto dall'approvazione e dall'aggiunta di nuovi tag.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
