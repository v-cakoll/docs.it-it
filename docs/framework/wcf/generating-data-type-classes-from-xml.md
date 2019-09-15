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
# <a name="generating-data-type-classes-from-xml"></a>Generazione di classi di tipo dati da XML
.NET Framework 4,5 include una nuova funzionalità per generare classi di tipi di dati da XML. In questo argomento viene descritto come generare automaticamente i tipi di dati per il feed RSS del Blog .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Recupero del codice XML dal feed RSS del Blog .NET  
  
1. In Internet Explorer passare al [feed RSS del Blog .NET](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Fare clic con il pulsante destro del mouse sulla pagina e scegliere **Visualizza origine**.  
  
3. Copiare il testo del feed premendo **CTRL + a** per selezionare tutto il testo e **CTRL + C** per copiarlo.  
  
### <a name="creating-the-data-types"></a>Creazione dei tipi di dati  
  
1. Aprire un file di codice in cui deve essere usato il proxy. Questo file deve far parte di un progetto .NET Framework 4,5.  
  
2. Posizionare il cursore nel file ma all'esterno di a qualsiasi classe esistente.  
  
3. Selezionare **modifica**, **Incolla speciale**, **Incolla XML come classi**.  
  
4. Le classi `link`denominate `rssChannelImage`, `rss` `rssChannel`, ,e`rssChannelItemGuid`vengono create con i membri necessari per accedere agli elementi nel feed RSS. `rssChannelItem`  
  
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
