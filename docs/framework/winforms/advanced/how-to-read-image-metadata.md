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
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988563"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="0f8a6-102">Procedura: Leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="0f8a6-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="0f8a6-103">Alcuni file di immagine contengono metadati che è possibile leggere per determinare le funzionalità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="0f8a6-104">Ad esempio, una fotografia digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e il modello della fotocamera usata per acquisire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="0f8a6-105">Con GDI+ è possibile leggere i metadati esistenti ed è anche possibile scrivere nuovi metadati nei file di immagine.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="0f8a6-106">In GDI+ viene archiviato un singolo elemento di metadati <xref:System.Drawing.Imaging.PropertyItem> in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="0f8a6-107">È possibile leggere la <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="0f8a6-108">La <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="0f8a6-109">Un <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le quattro proprietà seguenti: `Id`, `Value`, `Len`e `Type`.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="0f8a6-110">ID</span><span class="sxs-lookup"><span data-stu-id="0f8a6-110">Id</span></span>  
 <span data-ttu-id="0f8a6-111">Tag che identifica l'elemento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="0f8a6-112">Alcuni valori a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> cui è possibile assegnare sono riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="0f8a6-113">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="0f8a6-113">Hexadecimal value</span></span>|<span data-ttu-id="0f8a6-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0f8a6-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="0f8a6-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="0f8a6-115">0x0320</span></span><br /><br /> <span data-ttu-id="0f8a6-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="0f8a6-116">0x010F</span></span><br /><br /> <span data-ttu-id="0f8a6-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="0f8a6-117">0x0110</span></span><br /><br /> <span data-ttu-id="0f8a6-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="0f8a6-118">0x9003</span></span><br /><br /> <span data-ttu-id="0f8a6-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="0f8a6-119">0x829A</span></span><br /><br /> <span data-ttu-id="0f8a6-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="0f8a6-120">0x5090</span></span><br /><br /> <span data-ttu-id="0f8a6-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="0f8a6-121">0x5091</span></span>|<span data-ttu-id="0f8a6-122">Titolo immagine</span><span class="sxs-lookup"><span data-stu-id="0f8a6-122">Image title</span></span><br /><br /> <span data-ttu-id="0f8a6-123">Produttore apparecchiature</span><span class="sxs-lookup"><span data-stu-id="0f8a6-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="0f8a6-124">Modello Equipment</span><span class="sxs-lookup"><span data-stu-id="0f8a6-124">Equipment model</span></span><br /><br /> <span data-ttu-id="0f8a6-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="0f8a6-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="0f8a6-126">Tempo di esposizione EXIF</span><span class="sxs-lookup"><span data-stu-id="0f8a6-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="0f8a6-127">Tabella luminanza</span><span class="sxs-lookup"><span data-stu-id="0f8a6-127">Luminance table</span></span><br /><br /> <span data-ttu-id="0f8a6-128">Tabella cromatura</span><span class="sxs-lookup"><span data-stu-id="0f8a6-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="0f8a6-129">Value</span><span class="sxs-lookup"><span data-stu-id="0f8a6-129">Value</span></span>  
 <span data-ttu-id="0f8a6-130">Matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-130">An array of values.</span></span> <span data-ttu-id="0f8a6-131">Il formato dei valori è determinato dalla <xref:System.Drawing.Imaging.PropertyItem.Type%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="0f8a6-132">Len</span><span class="sxs-lookup"><span data-stu-id="0f8a6-132">Len</span></span>  
 <span data-ttu-id="0f8a6-133">Lunghezza in byte della matrice di valori a cui fa riferimento la <xref:System.Drawing.Imaging.PropertyItem.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="0f8a6-134">Type</span><span class="sxs-lookup"><span data-stu-id="0f8a6-134">Type</span></span>  
 <span data-ttu-id="0f8a6-135">Tipo di dati dei valori nella matrice a cui punta la `Value` proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="0f8a6-136">I formati indicati dai valori `Type` della proprietà sono riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="0f8a6-137">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="0f8a6-137">Numeric value</span></span>|<span data-ttu-id="0f8a6-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f8a6-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="0f8a6-139">1</span><span class="sxs-lookup"><span data-stu-id="0f8a6-139">1</span></span>|<span data-ttu-id="0f8a6-140">Elemento `Byte`</span><span class="sxs-lookup"><span data-stu-id="0f8a6-140">A `Byte`</span></span>|  
|<span data-ttu-id="0f8a6-141">2</span><span class="sxs-lookup"><span data-stu-id="0f8a6-141">2</span></span>|<span data-ttu-id="0f8a6-142">Matrice di `Byte` oggetti codificati come ASCII</span><span class="sxs-lookup"><span data-stu-id="0f8a6-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="0f8a6-143">3</span><span class="sxs-lookup"><span data-stu-id="0f8a6-143">3</span></span>|<span data-ttu-id="0f8a6-144">Intero A 16 bit</span><span class="sxs-lookup"><span data-stu-id="0f8a6-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="0f8a6-145">4</span><span class="sxs-lookup"><span data-stu-id="0f8a6-145">4</span></span>|<span data-ttu-id="0f8a6-146">Intero A 32 bit</span><span class="sxs-lookup"><span data-stu-id="0f8a6-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="0f8a6-147">5</span><span class="sxs-lookup"><span data-stu-id="0f8a6-147">5</span></span>|<span data-ttu-id="0f8a6-148">Matrice di due `Byte` oggetti che rappresentano un numero razionale</span><span class="sxs-lookup"><span data-stu-id="0f8a6-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="0f8a6-149">6</span><span class="sxs-lookup"><span data-stu-id="0f8a6-149">6</span></span>|<span data-ttu-id="0f8a6-150">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="0f8a6-150">Not used</span></span>|  
|<span data-ttu-id="0f8a6-151">7</span><span class="sxs-lookup"><span data-stu-id="0f8a6-151">7</span></span>|<span data-ttu-id="0f8a6-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="0f8a6-152">Undefined</span></span>|  
|<span data-ttu-id="0f8a6-153">8</span><span class="sxs-lookup"><span data-stu-id="0f8a6-153">8</span></span>|<span data-ttu-id="0f8a6-154">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="0f8a6-154">Not used</span></span>|  
|<span data-ttu-id="0f8a6-155">9</span><span class="sxs-lookup"><span data-stu-id="0f8a6-155">9</span></span>|`SLong`|  
|<span data-ttu-id="0f8a6-156">10</span><span class="sxs-lookup"><span data-stu-id="0f8a6-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="0f8a6-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f8a6-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0f8a6-158">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0f8a6-158">Description</span></span>  
 <span data-ttu-id="0f8a6-159">L'esempio di codice seguente legge e visualizza le sette parti di metadati nel file `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="0f8a6-160">Il secondo elemento della proprietà (indice 1) nell'elenco include <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Equipment Manufacturer) <xref:System.Drawing.Imaging.PropertyItem.Type%2A> e 2 (matrice di byte con codifica ASCII).</span><span class="sxs-lookup"><span data-stu-id="0f8a6-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="0f8a6-161">Nell'esempio di codice viene visualizzato il valore di tale elemento della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="0f8a6-162">Il codice produce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0f8a6-162">The code produces output similar to the following:</span></span>  
 
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
  
### <a name="code"></a><span data-ttu-id="0f8a6-163">Codice</span><span class="sxs-lookup"><span data-stu-id="0f8a6-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f8a6-164">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0f8a6-164">Compiling the Code</span></span>  
 <span data-ttu-id="0f8a6-165">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che <xref:System.Windows.Forms.Control.Paint> è un parametro del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0f8a6-166">Gestire l' <xref:System.Windows.Forms.Control.Paint> evento del form e incollare il codice nel gestore eventi Paint.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="0f8a6-167">È necessario sostituire `FakePhoto.jpg` con il nome e il percorso di un'immagine validi nel sistema e `System.Drawing.Imaging` importare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8a6-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f8a6-168">See also</span></span>

- [<span data-ttu-id="0f8a6-169">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="0f8a6-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="0f8a6-170">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="0f8a6-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
