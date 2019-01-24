---
title: 'Procedura: Impostare il livello di compressione JPEG'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: aae7be0b610ba90b5915267cd9bc257be9b56362
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628113"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="edda8-102">Procedura: Impostare il livello di compressione JPEG</span><span class="sxs-lookup"><span data-stu-id="edda8-102">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="edda8-103">Può essere opportuno modificare i parametri di un'immagine quando questa viene salvata sul disco per ridurre le dimensioni del file o migliorarne la qualità.</span><span class="sxs-lookup"><span data-stu-id="edda8-103">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="edda8-104">È possibile regolare la qualità di un'immagine JPEG modificandone il livello di compressione.</span><span class="sxs-lookup"><span data-stu-id="edda8-104">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="edda8-105">Per specificare il livello di compressione quando si salva un'immagine JPEG, è necessario creare un <xref:System.Drawing.Imaging.EncoderParameters> dell'oggetto e passarlo al <xref:System.Drawing.Image.Save%2A> metodo il <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="edda8-105">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="edda8-106">Inizializzare il <xref:System.Drawing.Imaging.EncoderParameters> oggetti in modo che abbia una matrice costituita da uno <xref:System.Drawing.Imaging.EncoderParameter>.</span><span class="sxs-lookup"><span data-stu-id="edda8-106">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="edda8-107">Quando si crea il <xref:System.Drawing.Imaging.EncoderParameter>, specificare il <xref:System.Drawing.Imaging.Encoder.Quality> codificatore e del livello di compressione desiderato.</span><span class="sxs-lookup"><span data-stu-id="edda8-107">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edda8-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="edda8-108">Example</span></span>  
 <span data-ttu-id="edda8-109">Il codice di esempio seguente crea un <xref:System.Drawing.Imaging.EncoderParameter> dell'oggetto e vengono salvate tre immagini JPEG.</span><span class="sxs-lookup"><span data-stu-id="edda8-109">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="edda8-110">Ogni immagine JPEG viene salvata con un livello di qualità diverso, modificando la `long` valore passato al <xref:System.Drawing.Imaging.EncoderParameter> costruttore.</span><span class="sxs-lookup"><span data-stu-id="edda8-110">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="edda8-111">Un livello di qualità pari a 0 corrisponde alla compressione massima, mentre un livello di qualità pari a 100 corrisponde alla compressione minima.</span><span class="sxs-lookup"><span data-stu-id="edda8-111">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageDecoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageDecoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="edda8-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="edda8-112">Compiling the Code</span></span>  
 <span data-ttu-id="edda8-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="edda8-113">This example requires:</span></span>  
  
-   <span data-ttu-id="edda8-114">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="edda8-114">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="edda8-115">Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="edda8-115">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
-   <span data-ttu-id="edda8-116">File di immagine denominato `TestPhoto.jpg` e archiviato in **c:\\**.</span><span class="sxs-lookup"><span data-stu-id="edda8-116">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edda8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edda8-117">See also</span></span>
- [<span data-ttu-id="edda8-118">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="edda8-118">How to: Determine the Parameters Supported by an Encoder</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="edda8-119">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="edda8-119">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
- [<span data-ttu-id="edda8-120">Uso di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="edda8-120">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
