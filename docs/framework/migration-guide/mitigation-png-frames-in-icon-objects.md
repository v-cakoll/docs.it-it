---
title: 'Attenuazione: Frame PNG in oggetti icona'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3ee5cc03f684acf103c96ecd14387f119bf0bdc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-png-frames-in-icon-objects"></a>Attenuazione: Frame PNG in oggetti icona
A partire da .NET Framework 4.6, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> converte correttamente le icone con i frame PNG in oggetti <xref:System.Drawing.Bitmap> .  
  
 Nelle app destinate a .NET Framework 4.5.2 e alle versioni precedenti, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.ArgumentOutOfRangeException> se l'oggetto <xref:System.Drawing.Icon> presenta frame PNG.  
  
## <a name="impact"></a>Impatto  
 Questa modifica influisce sulle app che vengono ricompilate per essere destinate a .NET Framework 4.6 e che implementano una gestione speciale per l'eccezione <xref:System.ArgumentOutOfRangeException> generata quando un oggetto <xref:System.Drawing.Icon> presenta frame PNG. Quando è in esecuzione su .NET Framework 4.6, la conversione viene completata correttamente, non viene più generata un'eccezione <xref:System.ArgumentOutOfRangeException> e quindi non viene più richiamato il gestore di eccezioni.  
  
### <a name="mitigation"></a>Mitigazione  
 Se questo comportamento è indesiderato, è possibile conservare il comportamento precedente aggiungendo l'elemento seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file app.config:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 Se il file app.config contiene già l'elemento `AppContextSwitchOverrides` , il nuovo valore deve essere unito con l'attributo `value` come nell'esempio seguente:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
