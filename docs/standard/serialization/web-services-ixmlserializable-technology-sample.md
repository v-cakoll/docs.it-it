---
title: Esempio di tecnologia IXmlSerializable dei servizi Web
ms.date: 03/30/2017
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
ms.openlocfilehash: eb117f720e7541ac6460b5adfd0eecc7901f4fdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582714"
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="04df3-102">Esempio di tecnologia IXmlSerializable dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="04df3-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="04df3-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="04df3-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="04df3-104">In questo esempio viene illustrato come utilizzare l'oggetto <xref:System.Xml.Serialization.IXmlSerializable> per controllare la serializzazione dei tipi personalizzati nei servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="04df3-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="04df3-105">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04df3-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="04df3-106">Aprire [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] e selezionare **Nuovo sito Web** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="04df3-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="04df3-107">Nel riquadro sinistro della finestra di dialogo **Nuovo sito Web** selezionare il linguaggio di programmazione desiderato e quindi nel riquadro destro selezionare **Servizio Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="04df3-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="04df3-108">Digitare **IXmlSerializable** come nome del nuovo servizio Web.</span><span class="sxs-lookup"><span data-stu-id="04df3-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="04df3-109">Nella finestra di Esplora soluzioni fare clic con il pulsante destro del mouse sull'icona relativa a Service.asmx e quindi scegliere **Elimina**. Ripetere questa operazione per il file code-behind Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="04df3-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="04df3-110">Fare clic con il pulsante destro del mouse sulla directory del progetto e scegliere **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="04df3-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="04df3-111">Nella finestra di dialogo spostarsi nella sottodirectory Service della directory specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="04df3-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="04df3-112">Fare clic su Service.asmx, quindi ripetere questa operazione per il file code-behind Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="04df3-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="04df3-113">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi nella directory contenente la directory IXmlSerializable creata al passaggio 3 precedente.</span><span class="sxs-lookup"><span data-stu-id="04df3-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="04df3-114">Fare clic con il pulsante destro del mouse sull'icona relativa alla directory IXmlSerializable e scegliere **Condivisione e sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="04df3-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="04df3-115">Nella scheda Condivisione Web selezionare **Condividi questa cartella** e confermare le impostazioni predefinite, incluso il nome IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="04df3-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="04df3-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="04df3-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="04df3-117">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="04df3-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="04df3-118">Aprire una finestra del browser, quindi fare clic sulla barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="04df3-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="04df3-119">Tipo **http://localhost/IXmlSerializable/Service.asmx**.</span><span class="sxs-lookup"><span data-stu-id="04df3-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04df3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04df3-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
