---
title: 'Procedura: leggere i metadati delle immagini'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9df2866251e08b8989f8550d045b587c9de8d2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-image-metadata"></a>Procedura: leggere i metadati delle immagini
Alcuni file di immagine contengono metadati che è possibile leggere per determinare le caratteristiche dell'immagine. Ad esempio, una foto digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e modello della fotocamera utilizzata per acquisire l'immagine. Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile leggere i metadati esistenti e ai file di immagine, è anche possibile scrivere nuovi metadati.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Archivia un metadato singolo in un <xref:System.Drawing.Imaging.PropertyItem> oggetto. È possibile leggere il <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file. Il <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.  
  
 Oggetto <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le seguenti quattro proprietà: `Id`, `Value`, `Len`, e `Type`.  
  
## <a name="id"></a>Id  
 Un tag che identifica l'elemento dei metadati. Alcuni valori che possono essere assegnati a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> vengono visualizzati nella tabella seguente.  
  
|Valore esadecimale|Descrizione|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Titolo dell'immagine<br /><br /> Produttore dell'hardware<br /><br /> Modello di apparecchiature<br /><br /> ExifDTOriginal<br /><br /> Tempo di esposizione EXIF<br /><br /> Tabella di luminanza<br /><br /> Tabella di saturazione|  
  
## <a name="value"></a>Valore  
 Una matrice di valori. Il formato dei valori è determinato dal <xref:System.Drawing.Imaging.PropertyItem.Type%2A> proprietà.  
  
## <a name="len"></a>Len  
 La lunghezza (in byte) della matrice di valori a cui punta il <xref:System.Drawing.Imaging.PropertyItem.Value%2A> proprietà.  
  
## <a name="type"></a>Tipo  
 Il tipo di dati dei valori nella matrice a cui punta il `Value` proprietà. I formati indicati dal `Type` i valori delle proprietà vengono visualizzati nella tabella seguente  
  
|Valore numerico|Descrizione|  
|-------------------|-----------------|  
|1|Elemento `Byte`|  
|2|Matrice di `Byte` oggetti codificati in ASCII|  
|3|Un integer a 16 bit|  
|4|Intero a 32 bit|  
|5|Una matrice di due `Byte` gli oggetti che rappresentano un numero razionale|  
|6|Non utilizzato|  
|7|Non definito|  
|8|Non utilizzato|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Esempio di codice seguente legge e visualizza le sette parti dei metadati nel file `FakePhoto.jpg`. Il secondo elemento della proprietà (indice 1) l'elenco contiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (produttore) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII). L'esempio di codice consente di visualizzare il valore dell'elemento proprietà.  
  
 Output del codice simile al seguente:  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a>Codice  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento e incollare questo codice nel gestore dell'evento paint. È necessario sostituire `FakePhoto.jpg` con un nome dell'immagine e un percorso valido per il sistema e l'importazione di `System.Drawing.Imaging` dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
