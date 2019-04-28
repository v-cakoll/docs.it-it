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
ms.openlocfilehash: 0a53e9b9d23c03715bf3088a4ae8577a39527995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672601"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="dc57c-102">Procedura: Leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="dc57c-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="dc57c-103">Alcuni file di immagine contengono metadati che è possibile leggere per determinare le caratteristiche dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="dc57c-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="dc57c-104">Scatta una foto digitale, ad esempio, potrebbe contenere i metadati che possono leggere per determinare la marca e modello di fotocamera usata per acquisire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="dc57c-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="dc57c-105">Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile leggere i metadati esistenti ed è anche possibile scrivere i nuovi metadati al file di immagine.</span><span class="sxs-lookup"><span data-stu-id="dc57c-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="dc57c-106">Archivia un'informazione di metadati in un <xref:System.Drawing.Imaging.PropertyItem> oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc57c-106">stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="dc57c-107">È possibile leggere il <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file.</span><span class="sxs-lookup"><span data-stu-id="dc57c-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="dc57c-108">Il <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="dc57c-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="dc57c-109">Oggetto <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le seguenti quattro proprietà: `Id`, `Value`, `Len`, e `Type`.</span><span class="sxs-lookup"><span data-stu-id="dc57c-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="dc57c-110">Id</span><span class="sxs-lookup"><span data-stu-id="dc57c-110">Id</span></span>  
 <span data-ttu-id="dc57c-111">Un tag che identifica l'elemento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="dc57c-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="dc57c-112">Alcuni valori che possono essere assegnati a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> vengono visualizzati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57c-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="dc57c-113">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="dc57c-113">Hexadecimal value</span></span>|<span data-ttu-id="dc57c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc57c-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="dc57c-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="dc57c-115">0x0320</span></span><br /><br /> <span data-ttu-id="dc57c-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="dc57c-116">0x010F</span></span><br /><br /> <span data-ttu-id="dc57c-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="dc57c-117">0x0110</span></span><br /><br /> <span data-ttu-id="dc57c-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="dc57c-118">0x9003</span></span><br /><br /> <span data-ttu-id="dc57c-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="dc57c-119">0x829A</span></span><br /><br /> <span data-ttu-id="dc57c-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="dc57c-120">0x5090</span></span><br /><br /> <span data-ttu-id="dc57c-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="dc57c-121">0x5091</span></span>|<span data-ttu-id="dc57c-122">Titolo dell'immagine</span><span class="sxs-lookup"><span data-stu-id="dc57c-122">Image title</span></span><br /><br /> <span data-ttu-id="dc57c-123">Casa produttrice dell'hardware</span><span class="sxs-lookup"><span data-stu-id="dc57c-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="dc57c-124">Modello delle apparecchiature</span><span class="sxs-lookup"><span data-stu-id="dc57c-124">Equipment model</span></span><br /><br /> <span data-ttu-id="dc57c-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="dc57c-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="dc57c-126">Tempo di esposizione EXIF</span><span class="sxs-lookup"><span data-stu-id="dc57c-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="dc57c-127">Tabella di luminosità</span><span class="sxs-lookup"><span data-stu-id="dc57c-127">Luminance table</span></span><br /><br /> <span data-ttu-id="dc57c-128">Tabella di cromatura</span><span class="sxs-lookup"><span data-stu-id="dc57c-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="dc57c-129">Value</span><span class="sxs-lookup"><span data-stu-id="dc57c-129">Value</span></span>  
 <span data-ttu-id="dc57c-130">Una matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="dc57c-130">An array of values.</span></span> <span data-ttu-id="dc57c-131">Il formato dei valori è determinato dal <xref:System.Drawing.Imaging.PropertyItem.Type%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc57c-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="dc57c-132">Len</span><span class="sxs-lookup"><span data-stu-id="dc57c-132">Len</span></span>  
 <span data-ttu-id="dc57c-133">La lunghezza (in byte) della matrice di valori a cui punta il <xref:System.Drawing.Imaging.PropertyItem.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc57c-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="dc57c-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc57c-134">Type</span></span>  
 <span data-ttu-id="dc57c-135">Il tipo di dati dei valori nella matrice a cui punta il `Value` proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc57c-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="dc57c-136">I formati indicati dal `Type` nella tabella seguente vengono visualizzati i valori delle proprietà</span><span class="sxs-lookup"><span data-stu-id="dc57c-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="dc57c-137">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="dc57c-137">Numeric value</span></span>|<span data-ttu-id="dc57c-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc57c-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="dc57c-139">1</span><span class="sxs-lookup"><span data-stu-id="dc57c-139">1</span></span>|<span data-ttu-id="dc57c-140">Elemento `Byte`</span><span class="sxs-lookup"><span data-stu-id="dc57c-140">A `Byte`</span></span>|  
|<span data-ttu-id="dc57c-141">2</span><span class="sxs-lookup"><span data-stu-id="dc57c-141">2</span></span>|<span data-ttu-id="dc57c-142">Matrice di `Byte` oggetti codificati in ASCII</span><span class="sxs-lookup"><span data-stu-id="dc57c-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="dc57c-143">3</span><span class="sxs-lookup"><span data-stu-id="dc57c-143">3</span></span>|<span data-ttu-id="dc57c-144">Un intero a 16 bit</span><span class="sxs-lookup"><span data-stu-id="dc57c-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="dc57c-145">4</span><span class="sxs-lookup"><span data-stu-id="dc57c-145">4</span></span>|<span data-ttu-id="dc57c-146">Un intero a 32 bit</span><span class="sxs-lookup"><span data-stu-id="dc57c-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="dc57c-147">5</span><span class="sxs-lookup"><span data-stu-id="dc57c-147">5</span></span>|<span data-ttu-id="dc57c-148">Una matrice di due `Byte` gli oggetti che rappresentano un numero razionale</span><span class="sxs-lookup"><span data-stu-id="dc57c-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="dc57c-149">6</span><span class="sxs-lookup"><span data-stu-id="dc57c-149">6</span></span>|<span data-ttu-id="dc57c-150">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="dc57c-150">Not used</span></span>|  
|<span data-ttu-id="dc57c-151">7</span><span class="sxs-lookup"><span data-stu-id="dc57c-151">7</span></span>|<span data-ttu-id="dc57c-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="dc57c-152">Undefined</span></span>|  
|<span data-ttu-id="dc57c-153">8</span><span class="sxs-lookup"><span data-stu-id="dc57c-153">8</span></span>|<span data-ttu-id="dc57c-154">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="dc57c-154">Not used</span></span>|  
|<span data-ttu-id="dc57c-155">9</span><span class="sxs-lookup"><span data-stu-id="dc57c-155">9</span></span>|`SLong`|  
|<span data-ttu-id="dc57c-156">10</span><span class="sxs-lookup"><span data-stu-id="dc57c-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="dc57c-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc57c-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dc57c-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc57c-158">Description</span></span>  
 <span data-ttu-id="dc57c-159">Esempio di codice seguente legge e visualizza i sette porzioni di metadati nel file `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="dc57c-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="dc57c-160">Il secondo elemento di proprietà (indice 1) nell'elenco contiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (produttrice dell'hardware) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII).</span><span class="sxs-lookup"><span data-stu-id="dc57c-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="dc57c-161">L'esempio di codice visualizza il valore di tale elemento di proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc57c-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="dc57c-162">Il codice restituisce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dc57c-162">The code produces output similar to the following:</span></span>  
  
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
  
### <a name="code"></a><span data-ttu-id="dc57c-163">Codice</span><span class="sxs-lookup"><span data-stu-id="dc57c-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc57c-164">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dc57c-164">Compiling the Code</span></span>  
 <span data-ttu-id="dc57c-165">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="dc57c-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="dc57c-166">Handle del modulo <xref:System.Windows.Forms.Control.Paint> evento e incollare questo codice nel gestore dell'evento paint.</span><span class="sxs-lookup"><span data-stu-id="dc57c-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="dc57c-167">È necessario sostituire `FakePhoto.jpg` con un nome di immagine e un percorso valido per il sistema e l'importazione di `System.Drawing.Imaging` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dc57c-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc57c-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc57c-168">See also</span></span>

- [<span data-ttu-id="dc57c-169">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="dc57c-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="dc57c-170">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="dc57c-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
