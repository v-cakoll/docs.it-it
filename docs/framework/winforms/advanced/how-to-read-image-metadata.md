---
title: 'Procedura: leggere i metadati delle immagini'
desription: Learn how to read the Windows Forms PropertyItems property of an Image object to retrieve all the metadata from a file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 814cb17feba1e1e3a42b2bc403b0b4c828caf90e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174666"
---
# <a name="how-to-read-image-metadata"></a>Procedura: leggere i metadati delle immagini

Alcuni file di immagine contengono metadati che è possibile leggere per determinare le funzionalità dell'immagine. Ad esempio, una fotografia digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e il modello della fotocamera usata per acquisire l'immagine. Con GDI+ è possibile leggere i metadati esistenti ed è anche possibile scrivere nuovi metadati nei file di immagine.

In GDI+ viene archiviato un singolo elemento di metadati in un <xref:System.Drawing.Imaging.PropertyItem> oggetto. È possibile leggere la <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file. La <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.

Un <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le quattro proprietà seguenti: `Id` , `Value` , `Len` e `Type` .

## <a name="id"></a>Id

Tag che identifica l'elemento dei metadati. Alcuni valori a cui è possibile assegnare <xref:System.Drawing.Imaging.PropertyItem.Id%2A> sono riportati nella tabella seguente:

|Valore esadecimale|Descrizione|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Titolo immagine<br /><br /> Produttore apparecchiature<br /><br /> Modello Equipment<br /><br /> ExifDTOriginal<br /><br /> Tempo di esposizione EXIF<br /><br /> Tabella luminanza<br /><br /> Tabella cromatura|

## <a name="value"></a>Valore

Matrice di valori . Il formato dei valori è determinato dalla <xref:System.Drawing.Imaging.PropertyItem.Type%2A> Proprietà.

## <a name="len"></a>Len

Lunghezza in byte della matrice di valori a cui fa riferimento la <xref:System.Drawing.Imaging.PropertyItem.Value%2A> Proprietà.

## <a name="type"></a>Type

Tipo di dati dei valori nella matrice a cui punta la `Value` Proprietà. I formati indicati dai `Type` valori della proprietà sono riportati nella tabella seguente:

|Valore numerico|Descrizione|
|-------------------|-----------------|
|1|`Byte`|
|2|Matrice di `Byte` oggetti codificati come ASCII|
|3|Intero A 16 bit|
|4|Intero A 32 bit|
|5|Matrice di due `Byte` oggetti che rappresentano un numero razionale|
|6|Non usato|
|7|Non definito|
|8|Non usato|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Esempio
  
L'esempio di codice seguente legge e visualizza le sette parti di metadati nel file `FakePhoto.jpg` . Il secondo elemento della proprietà (indice 1) nell'elenco include <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Equipment Manufacturer) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII). Nell'esempio di codice viene visualizzato il valore di tale elemento della proprietà.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

Il codice produce un output simile al seguente:

```output
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

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Gestire l'evento del form <xref:System.Windows.Forms.Control.Paint> e incollare il codice nel gestore eventi Paint. È necessario sostituire `FakePhoto.jpg` con il nome e il percorso di un'immagine validi nel sistema e importare lo `System.Drawing.Imaging` spazio dei nomi.

## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
