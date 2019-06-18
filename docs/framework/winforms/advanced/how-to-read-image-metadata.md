---
title: 'Procedura: Leggere i metadati delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 3266724503960b8b45cd134dfa5b007a58d578fa
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169805"
---
# <a name="how-to-read-image-metadata"></a>Procedura: Leggere i metadati delle immagini
Alcuni file di immagine contengono metadati che è possibile leggere per determinare le caratteristiche dell'immagine. Scatta una foto digitale, ad esempio, potrebbe contenere i metadati che possono leggere per determinare la marca e modello di fotocamera usata per acquisire l'immagine. Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile leggere i metadati esistenti ed è anche possibile scrivere i nuovi metadati al file di immagine.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Archivia un'informazione di metadati in un <xref:System.Drawing.Imaging.PropertyItem> oggetto. È possibile leggere il <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file. Il <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.  
  
 Oggetto <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le seguenti quattro proprietà: `Id`, `Value`, `Len`, e `Type`.  
  
## <a name="id"></a>Id  
 Un tag che identifica l'elemento dei metadati. Alcuni valori che possono essere assegnati a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> vengono visualizzati nella tabella seguente.  
  
|Valore esadecimale|Descrizione|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Titolo dell'immagine<br /><br /> Casa produttrice dell'hardware<br /><br /> Modello delle apparecchiature<br /><br /> ExifDTOriginal<br /><br /> Tempo di esposizione EXIF<br /><br /> Tabella di luminosità<br /><br /> Tabella di cromatura|  
  
## <a name="value"></a>Value  
 Una matrice di valori. Il formato dei valori è determinato dal <xref:System.Drawing.Imaging.PropertyItem.Type%2A> proprietà.  
  
## <a name="len"></a>Len  
 La lunghezza (in byte) della matrice di valori a cui punta il <xref:System.Drawing.Imaging.PropertyItem.Value%2A> proprietà.  
  
## <a name="type"></a>Tipo  
 Il tipo di dati dei valori nella matrice a cui punta il `Value` proprietà. I formati indicati dal `Type` nella tabella seguente vengono visualizzati i valori delle proprietà  
  
|Valore numerico|Descrizione|  
|-------------------|-----------------|  
|1|Elemento `Byte`|  
|2|Matrice di `Byte` oggetti codificati in ASCII|  
|3|Un intero a 16 bit|  
|4|Un intero a 32 bit|  
|5|Una matrice di due `Byte` gli oggetti che rappresentano un numero razionale|  
|6|Non utilizzato|  
|7|Undefined|  
|8|Non utilizzato|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Esempio di codice seguente legge e visualizza i sette porzioni di metadati nel file `FakePhoto.jpg`. Il secondo elemento di proprietà (indice 1) nell'elenco contiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (produttrice dell'hardware) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII). L'esempio di codice visualizza il valore di tale elemento di proprietà.  
  
 Il codice restituisce un output simile al seguente:  
 
```
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a>Codice  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Handle del modulo <xref:System.Windows.Forms.Control.Paint> evento e incollare questo codice nel gestore dell'evento paint. È necessario sostituire `FakePhoto.jpg` con un nome di immagine e un percorso valido per il sistema e l'importazione di `System.Drawing.Imaging` dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
