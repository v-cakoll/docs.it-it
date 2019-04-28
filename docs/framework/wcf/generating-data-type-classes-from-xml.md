---
title: Generazione di classi di tipo dati da XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c1b5dfda8aa5370dbc202ab90c75ab5677970467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929571"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="e1b7d-102">Generazione di classi di tipo dati da XML</span><span class="sxs-lookup"><span data-stu-id="e1b7d-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="e1b7d-103">include una nuova funzionalità per generare classi di tipi di dati da XML.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-103">includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="e1b7d-104">In questo argomento viene descritto come generare automaticamente i tipi di dati per feed RSS del Blog .NET.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="e1b7d-105">Acquisizione del codice XML dal RSS del Blog .NET feed</span><span class="sxs-lookup"><span data-stu-id="e1b7d-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="e1b7d-106">In Internet Explorer passare per il [feed RSS del Blog di .NET](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="e1b7d-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="e1b7d-107">La pagina e scegliere **Visualizza origine**.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="e1b7d-108">Copiare il testo del feed premendo **Ctrl + B** per selezionare tutto il testo, e **Ctrl + C** da copiare.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="e1b7d-109">Creazione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e1b7d-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="e1b7d-110">Aprire un file di codice in cui deve essere usato il proxy.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="e1b7d-111">Questo file deve far parte di un progetto [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1b7d-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2. <span data-ttu-id="e1b7d-112">Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="e1b7d-113">Selezionare **Edit**, **Incolla speciale**, **incolla XML come classi**.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="e1b7d-114">Classi denominate `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` e `rssChannelItemGuid` vengono creati con i membri necessari per l'accesso a elementi nel feed RSS.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="e1b7d-115">Uso delle classi generate</span><span class="sxs-lookup"><span data-stu-id="e1b7d-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="e1b7d-116">Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="e1b7d-117">Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="e1b7d-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
