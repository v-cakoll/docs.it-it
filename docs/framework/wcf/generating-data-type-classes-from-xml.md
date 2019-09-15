---
title: Generazione di classi di tipo dati da XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: bf5596211e78842153b7406273626a7fa3c3aeea
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990279"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="79601-102">Generazione di classi di tipo dati da XML</span><span class="sxs-lookup"><span data-stu-id="79601-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="79601-103">.NET Framework 4,5 include una nuova funzionalità per generare classi di tipi di dati da XML.</span><span class="sxs-lookup"><span data-stu-id="79601-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="79601-104">In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS del Blog .NET.</span><span class="sxs-lookup"><span data-stu-id="79601-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="79601-105">Recupero del codice XML dal feed RSS del Blog .NET</span><span class="sxs-lookup"><span data-stu-id="79601-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="79601-106">In Internet Explorer passare al [feed RSS del Blog .NET](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="79601-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="79601-107">Fare clic con il pulsante destro del mouse sulla pagina e scegliere **Visualizza origine**.</span><span class="sxs-lookup"><span data-stu-id="79601-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="79601-108">Copiare il testo del feed premendo **CTRL + a** per selezionare tutto il testo e **CTRL + C** per copiarlo.</span><span class="sxs-lookup"><span data-stu-id="79601-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="79601-109">Creazione dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="79601-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="79601-110">Aprire un file di codice in cui deve essere usato il proxy.</span><span class="sxs-lookup"><span data-stu-id="79601-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="79601-111">Questo file deve far parte di un progetto .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="79601-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="79601-112">Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.</span><span class="sxs-lookup"><span data-stu-id="79601-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="79601-113">Selezionare **modifica**, **Incolla speciale**, **Incolla XML come classi**.</span><span class="sxs-lookup"><span data-stu-id="79601-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="79601-114">Le classi `link`denominate `rssChannelImage`, `rss` `rssChannel`, ,e`rssChannelItemGuid`vengono create con i membri necessari per accedere agli elementi nel feed RSS. `rssChannelItem`</span><span class="sxs-lookup"><span data-stu-id="79601-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="79601-115">Uso delle classi generate</span><span class="sxs-lookup"><span data-stu-id="79601-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="79601-116">Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="79601-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="79601-117">Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="79601-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
