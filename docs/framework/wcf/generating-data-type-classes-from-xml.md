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
# <a name="generating-data-type-classes-from-xml"></a>Generazione di classi di tipo dati da XML
.NET Framework 4.5.NET Framework 4.5 include una nuova funzionalità per generare classi di tipi di dati da XML. In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS del blog di .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Recupero del codice XML dal feed RSS del blog di .NET  
  
1. In Internet Explorer passare al [feed RSS del blog di .NET.](https://devblogs.microsoft.com/dotnet/feed/)  
  
2. Fare clic con il pulsante destro del mouse sulla pagina e **scegliere Visualizza origine**.  
  
3. Copiate il testo del feed premendo **Ctrl ,A** per selezionare tutto il testo e **Ctrl .**  
  
### <a name="creating-the-data-types"></a>Creazione dei tipi di dati  
  
1. Aprire un file di codice in cui deve essere usato il proxy. Questo file deve far parte di un progetto .NET Framework 4.5.  
  
2. Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.  
  
3. Selezionare **Modifica**, **Incolla speciale**, **Incolla XML come classi**.  
  
4. Classi `link`denominate `rssChannel` `rssChannelImage`, `rssChannelItem` `rss` `rssChannelItemGuid` , , e vengono create con i membri necessari per accedere agli elementi nel feed RSS.  
  
### <a name="using-the-generated-classes"></a>Uso delle classi generate  
  
1. Una volta generate, le classi possono essere usate nel codice come qualsiasi altra classe. Nell'esempio di codice seguente viene restituita una nuova istanza della classe `rssChannelImage`.  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
