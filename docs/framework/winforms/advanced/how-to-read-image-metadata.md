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
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="7fbea-102">Procedura: leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="7fbea-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="7fbea-103">Alcuni file di immagine contengono metadati che è possibile leggere per determinare le caratteristiche dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="7fbea-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="7fbea-104">Ad esempio, una foto digitale potrebbe contenere metadati che è possibile leggere per determinare la marca e modello della fotocamera utilizzata per acquisire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="7fbea-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="7fbea-105">Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile leggere i metadati esistenti e ai file di immagine, è anche possibile scrivere nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="7fbea-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="7fbea-106">Archivia un metadato singolo in un <xref:System.Drawing.Imaging.PropertyItem> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7fbea-106"> stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="7fbea-107">È possibile leggere il <xref:System.Drawing.Image.PropertyItems%2A> proprietà di un <xref:System.Drawing.Image> oggetto per recuperare tutti i metadati da un file.</span><span class="sxs-lookup"><span data-stu-id="7fbea-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="7fbea-108">Il <xref:System.Drawing.Image.PropertyItems%2A> proprietà restituisce una matrice di <xref:System.Drawing.Imaging.PropertyItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7fbea-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="7fbea-109">Oggetto <xref:System.Drawing.Imaging.PropertyItem> oggetto ha le seguenti quattro proprietà: `Id`, `Value`, `Len`, e `Type`.</span><span class="sxs-lookup"><span data-stu-id="7fbea-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="7fbea-110">Id</span><span class="sxs-lookup"><span data-stu-id="7fbea-110">Id</span></span>  
 <span data-ttu-id="7fbea-111">Un tag che identifica l'elemento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="7fbea-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="7fbea-112">Alcuni valori che possono essere assegnati a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> vengono visualizzati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7fbea-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="7fbea-113">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="7fbea-113">Hexadecimal value</span></span>|<span data-ttu-id="7fbea-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbea-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="7fbea-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="7fbea-115">0x0320</span></span><br /><br /> <span data-ttu-id="7fbea-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="7fbea-116">0x010F</span></span><br /><br /> <span data-ttu-id="7fbea-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="7fbea-117">0x0110</span></span><br /><br /> <span data-ttu-id="7fbea-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="7fbea-118">0x9003</span></span><br /><br /> <span data-ttu-id="7fbea-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="7fbea-119">0x829A</span></span><br /><br /> <span data-ttu-id="7fbea-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="7fbea-120">0x5090</span></span><br /><br /> <span data-ttu-id="7fbea-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="7fbea-121">0x5091</span></span>|<span data-ttu-id="7fbea-122">Titolo dell'immagine</span><span class="sxs-lookup"><span data-stu-id="7fbea-122">Image title</span></span><br /><br /> <span data-ttu-id="7fbea-123">Produttore dell'hardware</span><span class="sxs-lookup"><span data-stu-id="7fbea-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="7fbea-124">Modello di apparecchiature</span><span class="sxs-lookup"><span data-stu-id="7fbea-124">Equipment model</span></span><br /><br /> <span data-ttu-id="7fbea-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="7fbea-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="7fbea-126">Tempo di esposizione EXIF</span><span class="sxs-lookup"><span data-stu-id="7fbea-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="7fbea-127">Tabella di luminanza</span><span class="sxs-lookup"><span data-stu-id="7fbea-127">Luminance table</span></span><br /><br /> <span data-ttu-id="7fbea-128">Tabella di saturazione</span><span class="sxs-lookup"><span data-stu-id="7fbea-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="7fbea-129">Valore</span><span class="sxs-lookup"><span data-stu-id="7fbea-129">Value</span></span>  
 <span data-ttu-id="7fbea-130">Una matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="7fbea-130">An array of values.</span></span> <span data-ttu-id="7fbea-131">Il formato dei valori è determinato dal <xref:System.Drawing.Imaging.PropertyItem.Type%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7fbea-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="7fbea-132">Len</span><span class="sxs-lookup"><span data-stu-id="7fbea-132">Len</span></span>  
 <span data-ttu-id="7fbea-133">La lunghezza (in byte) della matrice di valori a cui punta il <xref:System.Drawing.Imaging.PropertyItem.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7fbea-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="7fbea-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="7fbea-134">Type</span></span>  
 <span data-ttu-id="7fbea-135">Il tipo di dati dei valori nella matrice a cui punta il `Value` proprietà.</span><span class="sxs-lookup"><span data-stu-id="7fbea-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="7fbea-136">I formati indicati dal `Type` i valori delle proprietà vengono visualizzati nella tabella seguente</span><span class="sxs-lookup"><span data-stu-id="7fbea-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="7fbea-137">Valore numerico</span><span class="sxs-lookup"><span data-stu-id="7fbea-137">Numeric value</span></span>|<span data-ttu-id="7fbea-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbea-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="7fbea-139">1</span><span class="sxs-lookup"><span data-stu-id="7fbea-139">1</span></span>|<span data-ttu-id="7fbea-140">Elemento `Byte`</span><span class="sxs-lookup"><span data-stu-id="7fbea-140">A `Byte`</span></span>|  
|<span data-ttu-id="7fbea-141">2</span><span class="sxs-lookup"><span data-stu-id="7fbea-141">2</span></span>|<span data-ttu-id="7fbea-142">Matrice di `Byte` oggetti codificati in ASCII</span><span class="sxs-lookup"><span data-stu-id="7fbea-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="7fbea-143">3</span><span class="sxs-lookup"><span data-stu-id="7fbea-143">3</span></span>|<span data-ttu-id="7fbea-144">Un integer a 16 bit</span><span class="sxs-lookup"><span data-stu-id="7fbea-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="7fbea-145">4</span><span class="sxs-lookup"><span data-stu-id="7fbea-145">4</span></span>|<span data-ttu-id="7fbea-146">Intero a 32 bit</span><span class="sxs-lookup"><span data-stu-id="7fbea-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="7fbea-147">5</span><span class="sxs-lookup"><span data-stu-id="7fbea-147">5</span></span>|<span data-ttu-id="7fbea-148">Una matrice di due `Byte` gli oggetti che rappresentano un numero razionale</span><span class="sxs-lookup"><span data-stu-id="7fbea-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="7fbea-149">6</span><span class="sxs-lookup"><span data-stu-id="7fbea-149">6</span></span>|<span data-ttu-id="7fbea-150">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="7fbea-150">Not used</span></span>|  
|<span data-ttu-id="7fbea-151">7</span><span class="sxs-lookup"><span data-stu-id="7fbea-151">7</span></span>|<span data-ttu-id="7fbea-152">Non definito</span><span class="sxs-lookup"><span data-stu-id="7fbea-152">Undefined</span></span>|  
|<span data-ttu-id="7fbea-153">8</span><span class="sxs-lookup"><span data-stu-id="7fbea-153">8</span></span>|<span data-ttu-id="7fbea-154">Non utilizzato</span><span class="sxs-lookup"><span data-stu-id="7fbea-154">Not used</span></span>|  
|<span data-ttu-id="7fbea-155">9</span><span class="sxs-lookup"><span data-stu-id="7fbea-155">9</span></span>|`SLong`|  
|<span data-ttu-id="7fbea-156">10</span><span class="sxs-lookup"><span data-stu-id="7fbea-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="7fbea-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fbea-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7fbea-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbea-158">Description</span></span>  
 <span data-ttu-id="7fbea-159">Esempio di codice seguente legge e visualizza le sette parti dei metadati nel file `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="7fbea-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="7fbea-160">Il secondo elemento della proprietà (indice 1) l'elenco contiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (produttore) e <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matrice di byte con codifica ASCII).</span><span class="sxs-lookup"><span data-stu-id="7fbea-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="7fbea-161">L'esempio di codice consente di visualizzare il valore dell'elemento proprietà.</span><span class="sxs-lookup"><span data-stu-id="7fbea-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="7fbea-162">Output del codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7fbea-162">The code produces output similar to the following:</span></span>  
  
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
  
### <a name="code"></a><span data-ttu-id="7fbea-163">Codice</span><span class="sxs-lookup"><span data-stu-id="7fbea-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fbea-164">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7fbea-164">Compiling the Code</span></span>  
 <span data-ttu-id="7fbea-165">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="7fbea-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="7fbea-166">Gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento e incollare questo codice nel gestore dell'evento paint.</span><span class="sxs-lookup"><span data-stu-id="7fbea-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="7fbea-167">È necessario sostituire `FakePhoto.jpg` con un nome dell'immagine e un percorso valido per il sistema e l'importazione di `System.Drawing.Imaging` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7fbea-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbea-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbea-168">See Also</span></span>  
 [<span data-ttu-id="7fbea-169">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="7fbea-169">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="7fbea-170">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="7fbea-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
