---
title: Ordine di serializzazione personalizzato con XmlSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae5969060938763fee63c514de0a87eadbe6537a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="7bbb5-102">Ordine di serializzazione personalizzato con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="7bbb5-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="7bbb5-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="7bbb5-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="7bbb5-104">In questo esempio viene illustrato come controllare l'ordine degli elementi serializzati e deserializzati per la serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="7bbb5-105">Per ulteriori informazioni sulla serializzazione, vedere i commenti nei file di codice sorgente e build.proj.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="7bbb5-106">Per compilare l'esempio utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="7bbb5-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="7bbb5-107">Aprire la finestra del prompt dei comandi, quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="7bbb5-108">Digitare **msbuild CustomOrder.sln** dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="7bbb5-109">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7bbb5-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="7bbb5-110">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="7bbb5-111">Fare doppio clic sull'icona relativa a CustomOrder.sln per aprire il file in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="7bbb5-112">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="7bbb5-113">L'applicazione verrà compilata nella sottodirectory predefinita \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="7bbb5-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbb5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bbb5-114">See Also</span></span>  
 [<span data-ttu-id="7bbb5-115">Serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="7bbb5-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="7bbb5-116">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="7bbb5-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="7bbb5-117">Controllo della serializzazione XML mediante attributi</span><span class="sxs-lookup"><span data-stu-id="7bbb5-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="7bbb5-118">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="7bbb5-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="7bbb5-119">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="7bbb5-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="7bbb5-120">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="7bbb5-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
