---
title: Generazione di classi di tipo dati da XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: b99bb40105398dbd91b910c4a19828d069c3d9e7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380212"
---
# <a name="generating-data-type-classes-from-xml"></a>Generazione di classi di tipo dati da XML
.NET framework 4.5 include una nuova funzionalità per generare classi del tipo di dati da XML. In questo argomento viene descritto come generare automaticamente i tipi di dati per feed RSS del Blog .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Acquisizione del codice XML dal RSS del Blog .NET feed  
  
1. In Internet Explorer passare per il [feed RSS del Blog di .NET](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. La pagina e scegliere **Visualizza origine**.  
  
3. Copiare il testo del feed premendo **Ctrl + B** per selezionare tutto il testo, e **Ctrl + C** da copiare.  
  
### <a name="creating-the-data-types"></a>Creazione dei tipi di dati  
  
1. Aprire un file di codice in cui deve essere usato il proxy. Questo file deve far parte di un progetto di .NET Framework 4.5.  
  
2. Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.  
  
3. Selezionare **Edit**, **Incolla speciale**, **incolla XML come classi**.  
  
4. Classi denominate `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` e `rssChannelItemGuid` vengono creati con i membri necessari per l'accesso a elementi nel feed RSS.  
  
### <a name="using-the-generated-classes"></a>Uso delle classi generate  
  
1. Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe. Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
