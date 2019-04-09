---
title: 'Procedura: Determinare i parametri supportati da un codificatore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204575"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="372ce-102">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="372ce-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="372ce-103">È possibile modificare i parametri dell'immagine, ad esempio a livello di qualità e la compressione, ma è necessario conoscere quali parametri sono supportati da un codificatore di immagini specificato.</span><span class="sxs-lookup"><span data-stu-id="372ce-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="372ce-104">Il <xref:System.Drawing.Image> classe fornisce il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo in modo da poter determinare quali parametri dell'immagine sono supportate per un codificatore particolare.</span><span class="sxs-lookup"><span data-stu-id="372ce-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="372ce-105">Specificare il codificatore con un GUID.</span><span class="sxs-lookup"><span data-stu-id="372ce-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="372ce-106">Il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo restituisce una matrice di <xref:System.Drawing.Imaging.EncoderParameter> oggetti.</span><span class="sxs-lookup"><span data-stu-id="372ce-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="372ce-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="372ce-107">Example</span></span>  
 <span data-ttu-id="372ce-108">Esempio di codice seguente restituisce i parametri supportati per il codificatore JPEG.</span><span class="sxs-lookup"><span data-stu-id="372ce-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="372ce-109">Usare l'elenco delle categorie di parametro e i GUID associati nel <xref:System.Drawing.Imaging.Encoder> Cenni preliminari sulla classe per determinare la categoria per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="372ce-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="372ce-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="372ce-110">Compiling the Code</span></span>  
 <span data-ttu-id="372ce-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="372ce-111">This example requires:</span></span>  
  
-   <span data-ttu-id="372ce-112">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="372ce-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="372ce-113">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="372ce-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372ce-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="372ce-114">See also</span></span>

- [<span data-ttu-id="372ce-115">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="372ce-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="372ce-116">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="372ce-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="372ce-117">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="372ce-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
