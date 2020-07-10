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
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="da80d-102">Procedura: leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="da80d-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="da80d-103">Alcuni file di immagine contengono metadati che è possibile leggere per determinare le funzionalità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="da80d-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="da80d-104">Ad esempio, una fotografia digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e il modello della fotocamera usata per acquisire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="da80d-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="da80d-105">Con GDI+ è possibile leggere i metadati esistenti ed è anche possibile scrivere nuovi metadati nei file di immagine.</span><span class="sxs-lookup"><span data-stu-id="da80d-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="da80d-106">In GDI+ viene archiviato un singolo elemento di metadati in un <xref:System.Drawing.Imaging.PropertyItem> oggetto.</span><span class="sxs-lookup"><span data-stu-id="da80d-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="da80d-107">È possibile leggere la <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file.</span><span class="sxs-lookup"><span data-stu-id="da80d-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="da80d-108">La <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="da80d-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="da80d-109">Un <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le quattro proprietà seguenti: `Id` , `Value` , `Len` e `Type` .</span><span class="sxs-lookup"><span data-stu-id="da80d-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="da80d-110">Id</span><span class="sxs-lookup"><span data-stu-id="da80d-110">Id</span></span>

<span data-ttu-id="da80d-111">Tag che identifica l'elemento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="da80d-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="da80d-112">Alcuni valori a cui è possibile assegnare <xref:System.Drawing.Imaging.PropertyItem.Id%2A> sono riportati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="da80d-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="da80d-113">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="da80d-113">Hexadecimal value</span></span>|<span data-ttu-id="da80d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da80d-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="da80d-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="da80d-115">0x0320</span></span><br /><br /> <span data-ttu-id="da80d-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="da80d-116">0x010F</span></span><br /><br /> <span data-ttu-id="da80d-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="da80d-117">0x0110</span></span><br /><br /> <span data-ttu-id="da80d-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="da80d-118">0x9003</span></span><br /><br /> <span data-ttu-id="da80d-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="da80d-119">0x829A</span></span><br /><br /> <span data-ttu-id="da80d-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="da80d-120">0x5090</span></span><br /><br /> <span data-ttu-id="da80d-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="da80d-121">0x5091</span></span>|<span data-ttu-id="da80d-122">Titolo immagine</span><span class="sxs-lookup"><span data-stu-id="da80d-122">Image title</span></span><br /><br /> <span data-ttu-id="da80d-123">Produttore apparecchiature</span><span class="sxs-lookup"><span data-stu-id="da80d-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="da80d-124">Modello Equipment</span><span class="sxs-lookup"><span data-stu-id="da80d-124">Equipment model</span></span><br /><br /> <span data-ttu-id="da80d-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="da80d-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="da80d-126">Tempo di esposizione EXIF</span><span class="sxs-lookup"><span data-stu-id="da80d-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="da80d-127">Tabella luminanza</span><span class="sxs-lookup"><span data-stu-id="da80d-127">Luminance table</span></span><br /><br /> <span data-ttu-id="da80d-128">Tabella cromatura</span><span class="sxs-lookup"><span data-stu-id="da80d-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="da80d-129">Valore</span><span class="sxs-lookup"><span data-stu-id="da80d-129">Value</span></span>

<span data-ttu-id="da80d-130">Matrice di valori .</span><span class="sxs-lookup"><span data-stu-id="da80d-130">An array of values.</span></span> <span data-ttu-id="da80d-131">Il formato dei valori è determinato dalla <xref:System.Drawing.Imaging.PropertyItem.Type%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="da80d-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="da80d-132">Len</span><span class="sxs-lookup"><span data-stu-id="da80d-132">Len</span></span>

<span data-ttu-id="da80d-133">Lunghezza in byte della matrice di valori a cui fa riferimento la <xref:System.Drawing.Imaging.PropertyItem.Value%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="da80d-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="da80d-134">Type</span><span class="sxs-lookup"><span data-stu-id="da80d-134">Type</span></span>

<span data-ttu-id="da80d-135">Tipo di dati dei valori nella matrice a cui punta la `Value` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="da80d-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="da80d-136">I formati indicati dai `Type` valori della proprietà sono riportati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="da80d-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="da80d-137">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="da80d-137">Numeric value</span></span>|<span data-ttu-id="da80d-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da80d-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="da80d-139">1</span><span class="sxs-lookup"><span data-stu-id="da80d-139">1</span></span>|<span data-ttu-id="da80d-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="da80d-140">A `Byte`</span></span>|
|<span data-ttu-id="da80d-141">2</span><span class="sxs-lookup"><span data-stu-id="da80d-141">2</span></span>|<span data-ttu-id="da80d-142">Matrice di `Byte` oggetti codificati come ASCII</span><span class="sxs-lookup"><span data-stu-id="da80d-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="da80d-143">3</span><span class="sxs-lookup"><span data-stu-id="da80d-143">3</span></span>|<span data-ttu-id="da80d-144">Intero A 16 bit</span><span class="sxs-lookup"><span data-stu-id="da80d-144">A 16-bit integer</span></span>|
|<span data-ttu-id="da80d-145">4</span><span class="sxs-lookup"><span data-stu-id="da80d-145">4</span></span>|<span data-ttu-id="da80d-146">Intero A 32 bit</span><span class="sxs-lookup"><span data-stu-id="da80d-146">A 32-bit integer</span></span>|
|<span data-ttu-id="da80d-147">5</span><span class="sxs-lookup"><span data-stu-id="da80d-147">5</span></span>|<span data-ttu-id="da80d-148">Matrice di due `Byte` oggetti che rappresentano un numero razionale</span><span class="sxs-lookup"><span data-stu-id="da80d-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="da80d-149">6</span><span class="sxs-lookup"><span data-stu-id="da80d-149">6</span></span>|<span data-ttu-id="da80d-150">Non usato</span><span class="sxs-lookup"><span data-stu-id="da80d-150">Not used</span></span>|
|<span data-ttu-id="da80d-151">7</span><span class="sxs-lookup"><span data-stu-id="da80d-151">7</span></span>|<span data-ttu-id="da80d-152">Non definito</span><span class="sxs-lookup"><span data-stu-id="da80d-152">Undefined</span></span>|
|<span data-ttu-id="da80d-153">8</span><span class="sxs-lookup"><span data-stu-id="da80d-153">8</span></span>|<span data-ttu-id="da80d-154">Non usato</span><span class="sxs-lookup"><span data-stu-id="da80d-154">Not used</span></span>|
|<span data-ttu-id="da80d-155">9</span><span class="sxs-lookup"><span data-stu-id="da80d-155">9</span></span>|`SLong`|
|<span data-ttu-id="da80d-156">10</span><span class="sxs-lookup"><span data-stu-id="da80d-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="da80d-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="da80d-157">Example</span></span>
  
<span data-ttu-id="da80d-158">L'esempio di codice seguente legge e visualizza le sette parti di metadati nel file `FakePhoto.jpg` .</span><span class="sxs-lookup"><span data-stu-id="da80d-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="da80d-159">Il secondo elemento della proprietà (indice 1) nell'elenco include <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Equipment Manufacturer) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII).</span><span class="sxs-lookup"><span data-stu-id="da80d-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="da80d-160">Nell'esempio di codice viene visualizzato il valore di tale elemento della proprietà.</span><span class="sxs-lookup"><span data-stu-id="da80d-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="da80d-161">Il codice produce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="da80d-161">The code produces output similar to the following:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="da80d-162">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="da80d-162">Compiling the Code</span></span>

<span data-ttu-id="da80d-163">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="da80d-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="da80d-164">Gestire l'evento del form <xref:System.Windows.Forms.Control.Paint> e incollare il codice nel gestore eventi Paint.</span><span class="sxs-lookup"><span data-stu-id="da80d-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="da80d-165">È necessario sostituire `FakePhoto.jpg` con il nome e il percorso di un'immagine validi nel sistema e importare lo `System.Drawing.Imaging` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="da80d-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="da80d-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da80d-166">See also</span></span>

- [<span data-ttu-id="da80d-167">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="da80d-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="da80d-168">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="da80d-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
