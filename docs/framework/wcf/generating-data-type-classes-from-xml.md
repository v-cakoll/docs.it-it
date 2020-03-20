---
title: Generazione di classi di tipo dati da XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184125"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="6c8e8-102">Generazione di classi di tipo dati da XML</span><span class="sxs-lookup"><span data-stu-id="6c8e8-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="6c8e8-103">.NET Framework 4.5.NET Framework 4.5 include una nuova funzionalità per generare classi di tipi di dati da XML.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="6c8e8-104">In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS del blog di .NET.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="6c8e8-105">Recupero del codice XML dal feed RSS del blog di .NET</span><span class="sxs-lookup"><span data-stu-id="6c8e8-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="6c8e8-106">In Internet Explorer passare al [feed RSS del blog di .NET.](https://devblogs.microsoft.com/dotnet/feed/)</span><span class="sxs-lookup"><span data-stu-id="6c8e8-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="6c8e8-107">Fare clic con il pulsante destro del mouse sulla pagina e **scegliere Visualizza origine**.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="6c8e8-108">Copiate il testo del feed premendo **Ctrl ,A** per selezionare tutto il testo e **Ctrl .**</span><span class="sxs-lookup"><span data-stu-id="6c8e8-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="6c8e8-109">Creazione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6c8e8-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="6c8e8-110">Aprire un file di codice in cui deve essere usato il proxy.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="6c8e8-111">Questo file deve far parte di un progetto .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="6c8e8-112">Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="6c8e8-113">Selezionare **Modifica**, **Incolla speciale**, **Incolla XML come classi**.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="6c8e8-114">Classi `link`denominate `rssChannel` `rssChannelImage`, `rssChannelItem` `rss` `rssChannelItemGuid` , , e vengono create con i membri necessari per accedere agli elementi nel feed RSS.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="6c8e8-115">Uso delle classi generate</span><span class="sxs-lookup"><span data-stu-id="6c8e8-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="6c8e8-116">Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="6c8e8-117">Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="6c8e8-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
