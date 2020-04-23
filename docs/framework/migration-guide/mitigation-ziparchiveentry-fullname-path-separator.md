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
ms.openlocfilehash: 3f6c7f258fd5dbf01db4d79b73b88ddd7484f9b2
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102619"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a>Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName

A partire dalle app destinate a .NET Framework 4.6.1, il separatore di percorso utilizzato nella <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> proprietà è stato modificato dalla barra rovesciata ("\\") utilizzata nelle versioni precedenti di .NET Framework a una barra ("/"). Gli oggetti <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> vengono creati chiamando uno degli overload del metodo <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.  
  
## <a name="impact"></a>Impatto  
 Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.  
  
 La decompressione di un file zip creato da un'app destinata a una versione precedente di .NET Framework in sistemi operativi non Windows, ad esempio MacOS, non riesce a mantenere la struttura di directory. Ad esempio, in MacOS, crea un set di file il cui nome file\\concatena il percorso della directory, eventuali caratteri di barra rovesciata (" ") e il nome del file. Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.  
  
 L'impatto di questa modifica su . I file zip decompressi nel sistema operativo Windows dalle <xref:System.IO> API nello spazio dei nomi .NET Framework devono essere minimi, poiché\\queste API possono gestire senza problemi una barra ("/") o una barra rovesciata (" ") come carattere separatore di percorso.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 Se questo comportamento è indesiderato, è possibile rifiutare [ \<](../configure-apps/file-schema/runtime/runtime-element.md) esplicitamente aggiungendo un'impostazione di configurazione alla sezione>di runtime del file di configurazione dell'applicazione. Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di rifiuto.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 Inoltre, le app destinate alle versioni precedenti di .NET Framework ma in esecuzione in .NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo un'impostazione [ \<](../configure-apps/file-schema/runtime/runtime-element.md) di configurazione alla sezione>di runtime del file di configurazione dell'applicazione. Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di consenso.  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
