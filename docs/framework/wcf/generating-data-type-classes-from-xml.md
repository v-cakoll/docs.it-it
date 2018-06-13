---
title: Generazione di classi di tipo dati da XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: 6b38a0aea3101c70b3c3ec0c8feb4ee88018b64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498667"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="25f90-102">Generazione di classi di tipo dati da XML</span><span class="sxs-lookup"><span data-stu-id="25f90-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="25f90-103"> include una nuova funzionalità per generare classi di tipi di dati da XML.</span><span class="sxs-lookup"><span data-stu-id="25f90-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="25f90-104">In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS di Blog di .NET.</span><span class="sxs-lookup"><span data-stu-id="25f90-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="25f90-105">Acquisizione del codice XML dal .NET Blog RSS feed</span><span class="sxs-lookup"><span data-stu-id="25f90-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="25f90-106">In Internet Explorer, individuare il [feed RSS del Blog di .NET](https://blogs.msdn.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="25f90-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="25f90-107">Fare clic sulla pagina e selezionare **Visualizza origine**.</span><span class="sxs-lookup"><span data-stu-id="25f90-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="25f90-108">Copiare il testo del feed premendo **Ctrl + A** per selezionare tutto il testo e **Ctrl + C** da copiare.</span><span class="sxs-lookup"><span data-stu-id="25f90-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="25f90-109">Creazione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="25f90-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="25f90-110">Aprire un file di codice in cui deve essere usato il proxy.</span><span class="sxs-lookup"><span data-stu-id="25f90-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="25f90-111">Questo file deve far parte di un progetto [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25f90-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="25f90-112">Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.</span><span class="sxs-lookup"><span data-stu-id="25f90-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="25f90-113">Selezionare **modifica**, **Incolla speciale**, **incolla XML come classi**.</span><span class="sxs-lookup"><span data-stu-id="25f90-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="25f90-114">Classi denominate `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` e `rssChannelItemGuid` vengono creati con i membri necessari per l'accesso agli elementi nel feed RSS.</span><span class="sxs-lookup"><span data-stu-id="25f90-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="25f90-115">Uso delle classi generate</span><span class="sxs-lookup"><span data-stu-id="25f90-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="25f90-116">Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="25f90-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="25f90-117">Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="25f90-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
