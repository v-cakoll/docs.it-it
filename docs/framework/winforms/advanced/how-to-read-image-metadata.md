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
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="8c7a3-102">Procedura: leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="8c7a3-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="8c7a3-103">Alcuni file di immagine contengono metadati che è possibile leggere per determinare le funzionalità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="8c7a3-104">Ad esempio, una fotografia digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e il modello della fotocamera utilizzata per acquisire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="8c7a3-105">Con GDI, è possibile leggere i metadati esistenti ed è anche possibile scrivere nuovi metadati nei file di immagine.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="8c7a3-106">In un <xref:System.Drawing.Imaging.PropertyItem> oggetto viene archiviata una singola parte di metadati.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="8c7a3-107">È possibile <xref:System.Drawing.Image.PropertyItems%2A> leggere la <xref:System.Drawing.Image> proprietà di un oggetto per recuperare tutti i metadati da un file.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="8c7a3-108">La <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce <xref:System.Drawing.Imaging.PropertyItem> una matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="8c7a3-109">Un <xref:System.Drawing.Imaging.PropertyItem> oggetto dispone delle `Id`quattro `Value` `Len`proprietà `Type`seguenti: , , , e .</span><span class="sxs-lookup"><span data-stu-id="8c7a3-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="8c7a3-110">ID</span><span class="sxs-lookup"><span data-stu-id="8c7a3-110">Id</span></span>

<span data-ttu-id="8c7a3-111">Tag che identifica l'elemento di metadati.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="8c7a3-112">Alcuni valori che possono <xref:System.Drawing.Imaging.PropertyItem.Id%2A> essere assegnati a sono illustrati nella tabella seguente:Some values that can be assigned to are shown in the following table:</span><span class="sxs-lookup"><span data-stu-id="8c7a3-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="8c7a3-113">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="8c7a3-113">Hexadecimal value</span></span>|<span data-ttu-id="8c7a3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c7a3-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="8c7a3-115">0x0320 (in tissuma 0x0320)</span><span class="sxs-lookup"><span data-stu-id="8c7a3-115">0x0320</span></span><br /><br /> <span data-ttu-id="8c7a3-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="8c7a3-116">0x010F</span></span><br /><br /> <span data-ttu-id="8c7a3-117">0x0110 (informazioni in questo stati in due)</span><span class="sxs-lookup"><span data-stu-id="8c7a3-117">0x0110</span></span><br /><br /> <span data-ttu-id="8c7a3-118">0x9003 (in tiolo</span><span class="sxs-lookup"><span data-stu-id="8c7a3-118">0x9003</span></span><br /><br /> <span data-ttu-id="8c7a3-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="8c7a3-119">0x829A</span></span><br /><br /> <span data-ttu-id="8c7a3-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="8c7a3-120">0x5090</span></span><br /><br /> <span data-ttu-id="8c7a3-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="8c7a3-121">0x5091</span></span>|<span data-ttu-id="8c7a3-122">Titolo immagine</span><span class="sxs-lookup"><span data-stu-id="8c7a3-122">Image title</span></span><br /><br /> <span data-ttu-id="8c7a3-123">Produttore di apparecchiature</span><span class="sxs-lookup"><span data-stu-id="8c7a3-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="8c7a3-124">Modello di attrezzatura</span><span class="sxs-lookup"><span data-stu-id="8c7a3-124">Equipment model</span></span><br /><br /> <span data-ttu-id="8c7a3-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="8c7a3-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="8c7a3-126">Tempo di esposizione exif</span><span class="sxs-lookup"><span data-stu-id="8c7a3-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="8c7a3-127">Tavolo Luminance</span><span class="sxs-lookup"><span data-stu-id="8c7a3-127">Luminance table</span></span><br /><br /> <span data-ttu-id="8c7a3-128">Tabella crominanza</span><span class="sxs-lookup"><span data-stu-id="8c7a3-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="8c7a3-129">valore</span><span class="sxs-lookup"><span data-stu-id="8c7a3-129">Value</span></span>

<span data-ttu-id="8c7a3-130">Matrice di valori .</span><span class="sxs-lookup"><span data-stu-id="8c7a3-130">An array of values.</span></span> <span data-ttu-id="8c7a3-131">Il formato dei valori è <xref:System.Drawing.Imaging.PropertyItem.Type%2A> determinato dalla proprietà .</span><span class="sxs-lookup"><span data-stu-id="8c7a3-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="8c7a3-132">Len</span><span class="sxs-lookup"><span data-stu-id="8c7a3-132">Len</span></span>

<span data-ttu-id="8c7a3-133">Lunghezza (in byte) della matrice di valori <xref:System.Drawing.Imaging.PropertyItem.Value%2A> a cui punta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="8c7a3-134">Type</span><span class="sxs-lookup"><span data-stu-id="8c7a3-134">Type</span></span>

<span data-ttu-id="8c7a3-135">Tipo di dati dei valori nella matrice `Value` a cui punta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="8c7a3-136">I formati indicati `Type` dai valori delle proprietà sono riportati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8c7a3-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="8c7a3-137">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="8c7a3-137">Numeric value</span></span>|<span data-ttu-id="8c7a3-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c7a3-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="8c7a3-139">1</span><span class="sxs-lookup"><span data-stu-id="8c7a3-139">1</span></span>|<span data-ttu-id="8c7a3-140">Come `Byte`</span><span class="sxs-lookup"><span data-stu-id="8c7a3-140">A `Byte`</span></span>|
|<span data-ttu-id="8c7a3-141">2</span><span class="sxs-lookup"><span data-stu-id="8c7a3-141">2</span></span>|<span data-ttu-id="8c7a3-142">Matrice di `Byte` oggetti codificati come ASCII</span><span class="sxs-lookup"><span data-stu-id="8c7a3-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="8c7a3-143">3</span><span class="sxs-lookup"><span data-stu-id="8c7a3-143">3</span></span>|<span data-ttu-id="8c7a3-144">Un numero intero a 16 bit</span><span class="sxs-lookup"><span data-stu-id="8c7a3-144">A 16-bit integer</span></span>|
|<span data-ttu-id="8c7a3-145">4</span><span class="sxs-lookup"><span data-stu-id="8c7a3-145">4</span></span>|<span data-ttu-id="8c7a3-146">Un numero intero a 32 bit</span><span class="sxs-lookup"><span data-stu-id="8c7a3-146">A 32-bit integer</span></span>|
|<span data-ttu-id="8c7a3-147">5</span><span class="sxs-lookup"><span data-stu-id="8c7a3-147">5</span></span>|<span data-ttu-id="8c7a3-148">Matrice di `Byte` due oggetti che rappresentano un numero razionale</span><span class="sxs-lookup"><span data-stu-id="8c7a3-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="8c7a3-149">6</span><span class="sxs-lookup"><span data-stu-id="8c7a3-149">6</span></span>|<span data-ttu-id="8c7a3-150">Non usato</span><span class="sxs-lookup"><span data-stu-id="8c7a3-150">Not used</span></span>|
|<span data-ttu-id="8c7a3-151">7</span><span class="sxs-lookup"><span data-stu-id="8c7a3-151">7</span></span>|<span data-ttu-id="8c7a3-152">Non definito</span><span class="sxs-lookup"><span data-stu-id="8c7a3-152">Undefined</span></span>|
|<span data-ttu-id="8c7a3-153">8</span><span class="sxs-lookup"><span data-stu-id="8c7a3-153">8</span></span>|<span data-ttu-id="8c7a3-154">Non usato</span><span class="sxs-lookup"><span data-stu-id="8c7a3-154">Not used</span></span>|
|<span data-ttu-id="8c7a3-155">9</span><span class="sxs-lookup"><span data-stu-id="8c7a3-155">9</span></span>|`SLong`|
|<span data-ttu-id="8c7a3-156">10</span><span class="sxs-lookup"><span data-stu-id="8c7a3-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="8c7a3-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c7a3-157">Example</span></span>
  
<span data-ttu-id="8c7a3-158">Nell'esempio di codice riportato di seguito vengono `FakePhoto.jpg`lette e visualizzate le sette parti di metadati nel file .</span><span class="sxs-lookup"><span data-stu-id="8c7a3-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="8c7a3-159">Il secondo elemento della proprietà (indice <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 1) nell'elenco ha 0x010F (produttore di apparecchiature) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII).</span><span class="sxs-lookup"><span data-stu-id="8c7a3-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="8c7a3-160">Nell'esempio di codice viene visualizzato il valore di tale elemento proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="8c7a3-161">Il codice produce un output simile al seguente:The code produces output similar to the following:</span><span class="sxs-lookup"><span data-stu-id="8c7a3-161">The code produces output similar to the following:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="8c7a3-162">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8c7a3-162">Compiling the Code</span></span>

<span data-ttu-id="8c7a3-163">L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8c7a3-164">Gestire l'evento <xref:System.Windows.Forms.Control.Paint> del form e incollare il codice nel gestore eventi paint.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="8c7a3-165">È necessario `FakePhoto.jpg` sostituire con un nome di immagine `System.Drawing.Imaging` e un percorso validi nel sistema e importare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8c7a3-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c7a3-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c7a3-166">See also</span></span>

- [<span data-ttu-id="8c7a3-167">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="8c7a3-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="8c7a3-168">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="8c7a3-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
