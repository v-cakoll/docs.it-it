---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614831"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Accessibilità migliorata per alcuni strumenti di .NET SDK

#### <a name="details"></a>Dettagli

In .NET Framework SDK 4.7.1 gli strumenti SvcConfigEditor.exe e SvcTraceViewer.exe sono stati migliorati risolvendo vari problemi relativi all'accessibilità. Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni pattern dell'automazione interfaccia utente non implementati correttamente. Sebbene molti utenti non siano a conoscenza di questi valori non corretti, i clienti che usano tecnologie per l'accesso facilitato, ad esempio gli utilità per la lettura dello schermo, troveranno questi strumenti SDK più accessibili Queste correzioni modificano sicuramente alcuni comportamenti precedenti, ad esempio l'ordine dello stato attivo della tastiera. Per ottenere tutte le correzioni relative all'accessibilità in questi strumenti, è possibile applicare quanto segue al file app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.1       |
| Type    | Ridestinazione |
