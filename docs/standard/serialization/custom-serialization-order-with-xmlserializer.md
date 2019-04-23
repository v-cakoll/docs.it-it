---
title: Ordine di serializzazione personalizzato con XmlSerializer
ms.date: 03/30/2017
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
ms.openlocfilehash: f63d460163c33c4253cf565a5755babc1030164f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295035"
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="6f3e1-102">Ordine di serializzazione personalizzato con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="6f3e1-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="6f3e1-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="6f3e1-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="6f3e1-104">In questo esempio viene illustrato come controllare l'ordine degli elementi serializzati e deserializzati per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="6f3e1-105">Per ulteriori informazioni sulla serializzazione, vedere i commenti nei file di codice sorgente e build.proj.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="6f3e1-106">Per compilare l'esempio utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="6f3e1-106">To build the sample using the Command Prompt</span></span>  
  
1. <span data-ttu-id="6f3e1-107">Aprire la finestra del prompt dei comandi, quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="6f3e1-108">Digitare **msbuild CustomOrder.sln** dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="6f3e1-109">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f3e1-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="6f3e1-110">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="6f3e1-111">Fare doppio clic sull'icona relativa a CustomOrder.sln per aprire il file in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="6f3e1-112">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4. <span data-ttu-id="6f3e1-113">L'applicazione verrà compilata nella sottodirectory predefinita \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="6f3e1-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3e1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f3e1-114">See also</span></span>

- [<span data-ttu-id="6f3e1-115">Serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="6f3e1-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="6f3e1-116">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="6f3e1-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="6f3e1-117">Controllo della serializzazione XML mediante attributi</span><span class="sxs-lookup"><span data-stu-id="6f3e1-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="6f3e1-118">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="6f3e1-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="6f3e1-119">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="6f3e1-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="6f3e1-120">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="6f3e1-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
