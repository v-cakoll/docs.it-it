---
title: 'Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
ms.openlocfilehash: 495377403e2f0c0f5f4f166f51d738265c16ef7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126052"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName
A partire dalle applicazioni che hanno come destinazione .NET Framework 4.6.1, il separatore di percorso usato nella proprietà <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> è stato modificato dalla barra rovesciata ("\\"), usata nelle versioni precedenti di .NET Framework, in una barra ("/").   Gli oggetti <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> vengono creati chiamando uno degli overload del metodo <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.  
  
## <a name="impact"></a>Impatto  
 Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.  
  
 La decompressione di un file zip creato da un'applicazione che ha come destinazione una versione precedente di .NET Framework nei sistemi operativi non Windows quali Macintosh non riesce a mantenere la struttura della directory. Ad esempio, su Macintosh, crea un set di file il cui nome concatena il percorso della directory, insieme a qualsiasi barra rovesciata ("\\") e al nome del file. Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.  
  
 L'impatto di questa modifica sui file ZIP che vengono decompressi nel sistema operativo Windows dalle API nello spazio dei nomi .NET Framework <xref:System.IO> dovrebbe essere minimo, poiché queste API possono gestire facilmente una barra ("/") o una barra rovesciata ("\\") come carattere separatore di percorso.  
  
## <a name="mitigation"></a>Attenuazione  
 Se questo comportamento è inaccettabile, è possibile scegliere di aggiungere un'impostazione di configurazione per la sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione. Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di rifiuto.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Inoltre, le app destinate a versioni precedenti di .NET Framework ma in esecuzione su NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo un'impostazione di configurazione alla sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione. Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di consenso.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Modifiche di reindirizzamento](retargeting-changes-in-the-net-framework-4-6-1.md)
- [Compatibilità delle applicazioni nella versione 4.6.1](application-compatibility-in-the-net-framework-4-6-1.md)
