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
# <a name="generating-data-type-classes-from-xml"></a>Generazione di classi di tipo dati da XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] include una nuova funzionalità per generare classi di tipi di dati da XML. In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS di Blog di .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Acquisizione del codice XML dal .NET Blog RSS feed  
  
1.  In Internet Explorer, individuare il [feed RSS del Blog di .NET](https://blogs.msdn.microsoft.com/dotnet/feed/).  
  
2.  Fare clic sulla pagina e selezionare **Visualizza origine**.  
  
3.  Copiare il testo del feed premendo **Ctrl + A** per selezionare tutto il testo e **Ctrl + C** da copiare.  
  
### <a name="creating-the-data-types"></a>Creazione dei tipi di dati  
  
1.  Aprire un file di codice in cui deve essere usato il proxy. Questo file deve far parte di un progetto [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
2.  Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.  
  
3.  Selezionare **modifica**, **Incolla speciale**, **incolla XML come classi**.  
  
4.  Classi denominate `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` e `rssChannelItemGuid` vengono creati con i membri necessari per l'accesso agli elementi nel feed RSS.  
  
### <a name="using-the-generated-classes"></a>Uso delle classi generate  
  
1.  Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe. Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
