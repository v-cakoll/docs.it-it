---
title: 'Mitigazione: Layout WPF'
description: Viene illustrato come attenuare i problemi derivanti da una modifica nel layout dei controlli WPF, ad esempio la posizione di un oggetto che si sposta di un pixel.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: e4e4612f7b39eefbf0e76ac86c8eb644c257ba75
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475346"
---
# <a name="mitigation-wpf-layout"></a>Mitigazione: Layout WPF
Il layout dei controlli WPF può cambiare leggermente.  
  
## <a name="impact"></a>Impatto  
 Come conseguenza di questo cambiamento:  
  
- La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.  
  
- La posizione di un oggetto può cambiare al massimo di un pixel.  
  
- Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.  
  
 Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Le app destinate a .NET Framework 4.6 ma che richiedono che il rendering dei controlli WPF venga eseguito mediante l'algoritmo di layout precedente possono aggiungere a questo scopo la riga seguente alla sezione `<runtime>` del file app.config:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
