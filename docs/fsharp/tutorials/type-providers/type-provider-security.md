---
title: Sicurezza dei provider di tipi
description: 'Informazioni sulla sicurezza dei provider di tipi in F #, incluso come modificare le impostazioni di trust per un provider di tipi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a>Sicurezza dei provider di tipi

Provider di tipi sono assembly (DLL) a cui fa riferimento il progetto F # o uno script che contengono codice per la connessione alle origini dati esterne e l'area di questo tipo di informazioni per l'ambiente di tipo F #. In genere, codice negli assembly di riferimento viene eseguito solo quando si compila e quindi eseguire il codice (o nel caso di uno script, inviare il codice di F # Interactive). Tuttavia, un assembly di provider di tipo verrà eseguita all'interno di Visual Studio quando il codice è semplicemente visualizzato nell'editor. Ciò accade perché i provider di tipo devono eseguire per aggiungere informazioni aggiuntive per l'editor, ad esempio le descrizioni comandi informazioni rapide, al completamento di IntelliSense e così via. Di conseguenza, esistono considerazioni sulla protezione aggiuntiva per il tipo di assembly del provider, poiché vengono eseguiti automaticamente all'interno del processo di Visual Studio.


## <a name="security-warning-dialog"></a>Avviso di sicurezza
Quando si utilizza un assembly di provider di tipo specifico per la prima volta, Visual Studio visualizza una finestra di dialogo di sicurezza in cui si segnala che il provider di tipi sta per eseguire. Prima di Visual Studio carica il provider di tipi, offre la possibilità di decidere se si considera attendibile questo provider. Se si ritiene attendibile l'origine del provider di tipi, quindi selezionare "Fiducia questo provider di tipi". Se si ritiene attendibile l'origine del provider di tipi, quindi selezionare "Non attendibile questo provider di tipi." Considerare attendibile il provider consente di eseguire in Visual Studio e fornire IntelliSense e compilare funzionalità. Tuttavia, se il provider di tipo stesso è dannoso, in esecuzione il codice potrebbe compromettere il computer.

Se il progetto contiene codice che fa riferimento a provider di tipi che si è scelto nella finestra di dialogo non considerare attendibile, quindi in fase di compilazione, il compilatore segnalerà un errore che indica che il provider di tipi non è attendibile. Tutti i tipi che dipendono dal provider di tipi non attendibili sono indicati da sottolineature rosse. È consigliabile esaminare il codice nell'editor.

Se si decide di modificare l'impostazione di attendibilità direttamente in Visual Studio, eseguire la procedura seguente.


#### <a name="to-change-the-trust-settings-for-type-providers"></a>Per modificare le impostazioni di trust per i provider di tipi

1. Nel `Tools` dal menu `Options`, espandere il `F# Tools` nodo.
<br />

2. Selezionare `Type Providers`, nell'elenco di provider di tipi, selezionare la casella di controllo per i provider di tipi è attendibile e deselezionare la casella di controllo per quelli non attendibili.
<br />


## <a name="see-also"></a>Vedere anche
[Provider di tipi](index.md)
