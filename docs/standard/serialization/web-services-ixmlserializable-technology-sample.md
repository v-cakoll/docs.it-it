---
title: Esempio di tecnologia IXmlSerializable dei servizi Web
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ce34f101efc4f439b83e9a1ed69d286971486e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="4d0d6-102">Esempio di tecnologia IXmlSerializable dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="4d0d6-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="4d0d6-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4d0d6-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="4d0d6-104">In questo esempio viene illustrato come utilizzare l'oggetto <xref:System.Xml.Serialization.IXmlSerializable> per controllare la serializzazione dei tipi personalizzati nei servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="4d0d6-105">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d0d6-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="4d0d6-106">Aprire [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] e selezionare **Nuovo sito Web** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="4d0d6-107">Nel riquadro sinistro della finestra di dialogo **Nuovo sito Web** selezionare il linguaggio di programmazione desiderato e quindi nel riquadro destro selezionare **Servizio Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="4d0d6-108">Digitare **IXmlSerializable** come nome del nuovo servizio Web.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="4d0d6-109">Nella finestra di Esplora soluzioni fare clic con il pulsante destro del mouse sull'icona relativa a Service.asmx e quindi scegliere **Elimina**. Ripetere questa operazione per il file code-behind Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="4d0d6-110">Fare clic con il pulsante destro del mouse sulla directory del progetto e scegliere **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="4d0d6-111">Nella finestra di dialogo spostarsi nella sottodirectory Service della directory specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="4d0d6-112">Fare clic su Service.asmx, quindi ripetere questa operazione per il file code-behind Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="4d0d6-113">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi nella directory contenente la directory IXmlSerializable creata al passaggio 3 precedente.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="4d0d6-114">Fare clic con il pulsante destro del mouse sull'icona relativa alla directory IXmlSerializable e scegliere **Condivisione e sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="4d0d6-115">Nella scheda Condivisione Web selezionare **Condividi questa cartella** e confermare le impostazioni predefinite, incluso il nome IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="4d0d6-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="4d0d6-117">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4d0d6-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="4d0d6-118">Aprire una finestra del browser, quindi fare clic sulla barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="4d0d6-119">Digitare **http://localhost/IXmlSerializable/Service.asmx**.</span><span class="sxs-lookup"><span data-stu-id="4d0d6-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0d6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d0d6-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
