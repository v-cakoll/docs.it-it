---
title: 'Procedura: leggere i metadati delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182514"
---
# <a name="how-to-read-image-metadata"></a>Procedura: leggere i metadati delle immagini

Alcuni file di immagine contengono metadati che è possibile leggere per determinare le funzionalità dell'immagine. Ad esempio, una fotografia digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e il modello della fotocamera utilizzata per acquisire l'immagine. Con GDI, è possibile leggere i metadati esistenti ed è anche possibile scrivere nuovi metadati nei file di immagine.

In un <xref:System.Drawing.Imaging.PropertyItem> oggetto viene archiviata una singola parte di metadati. È possibile <xref:System.Drawing.Image.PropertyItems%2A> leggere la <xref:System.Drawing.Image> proprietà di un oggetto per recuperare tutti i metadati da un file. La <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce <xref:System.Drawing.Imaging.PropertyItem> una matrice di oggetti.

Un <xref:System.Drawing.Imaging.PropertyItem> oggetto dispone delle `Id`quattro `Value` `Len`proprietà `Type`seguenti: , , , e .

## <a name="id"></a>ID

Tag che identifica l'elemento di metadati. Alcuni valori che possono <xref:System.Drawing.Imaging.PropertyItem.Id%2A> essere assegnati a sono illustrati nella tabella seguente:Some values that can be assigned to are shown in the following table:

|Valore esadecimale|Descrizione|
|-----------------------|-----------------|
|0x0320 (in tissuma 0x0320)<br /><br /> 0x010F<br /><br /> 0x0110 (informazioni in questo stati in due)<br /><br /> 0x9003 (in tiolo<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Titolo immagine<br /><br /> Produttore di apparecchiature<br /><br /> Modello di attrezzatura<br /><br /> ExifDTOriginal<br /><br /> Tempo di esposizione exif<br /><br /> Tavolo Luminance<br /><br /> Tabella crominanza|

## <a name="value"></a>valore

Matrice di valori . Il formato dei valori è <xref:System.Drawing.Imaging.PropertyItem.Type%2A> determinato dalla proprietà .

## <a name="len"></a>Len

Lunghezza (in byte) della matrice di valori <xref:System.Drawing.Imaging.PropertyItem.Value%2A> a cui punta la proprietà.

## <a name="type"></a>Type

Tipo di dati dei valori nella matrice `Value` a cui punta la proprietà. I formati indicati `Type` dai valori delle proprietà sono riportati nella tabella seguente:

|Valore numerico|Descrizione|
|-------------------|-----------------|
|1|Come `Byte`|
|2|Matrice di `Byte` oggetti codificati come ASCII|
|3|Un numero intero a 16 bit|
|4|Un numero intero a 32 bit|
|5|Matrice di `Byte` due oggetti che rappresentano un numero razionale|
|6|Non usato|
|7|Non definito|
|8|Non usato|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Esempio
  
Nell'esempio di codice riportato di seguito vengono `FakePhoto.jpg`lette e visualizzate le sette parti di metadati nel file . Il secondo elemento della proprietà (indice <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 1) nell'elenco ha 0x010F (produttore di apparecchiature) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII). Nell'esempio di codice viene visualizzato il valore di tale elemento proprietà.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

Il codice produce un output simile al seguente:The code produces output similar to the following:

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

L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Gestire l'evento <xref:System.Windows.Forms.Control.Paint> del form e incollare il codice nel gestore eventi paint. È necessario `FakePhoto.jpg` sostituire con un nome di immagine `System.Drawing.Imaging` e un percorso validi nel sistema e importare lo spazio dei nomi.

## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
