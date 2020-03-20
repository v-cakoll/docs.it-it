---
title: 'Attenuazione: Frame PNG in oggetti icona'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: d661e45bfbbe5e1c5ca5b7eb123e71aa32a096ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181215"
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="6c420-102">Attenuazione: Frame PNG in oggetti icona</span><span class="sxs-lookup"><span data-stu-id="6c420-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="6c420-103">A partire da .NET Framework 4.6, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> converte correttamente le icone con i frame PNG in oggetti <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="6c420-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="6c420-104">Nelle app destinate a .NET Framework 4.5.2 e alle versioni precedenti, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.ArgumentOutOfRangeException> se l'oggetto <xref:System.Drawing.Icon> presenta frame PNG.</span><span class="sxs-lookup"><span data-stu-id="6c420-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="6c420-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="6c420-105">Impact</span></span>  
 <span data-ttu-id="6c420-106">Questa modifica influisce sulle app che vengono ricompilate per essere destinate a .NET Framework 4.6 e che implementano una gestione speciale per l'eccezione <xref:System.ArgumentOutOfRangeException> generata quando un oggetto <xref:System.Drawing.Icon> presenta frame PNG.</span><span class="sxs-lookup"><span data-stu-id="6c420-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="6c420-107">Quando è in esecuzione su .NET Framework 4.6, la conversione viene completata correttamente, non viene più generata un'eccezione <xref:System.ArgumentOutOfRangeException> e quindi non viene più richiamato il gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6c420-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="6c420-108">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="6c420-108">Mitigation</span></span>  
 <span data-ttu-id="6c420-109">Se questo comportamento è indesiderato, è possibile mantenere il comportamento precedente aggiungendo l'elemento seguente alla sezione [ \<>di runtime](../configure-apps/file-schema/runtime/runtime-element.md) del file app.config:</span><span class="sxs-lookup"><span data-stu-id="6c420-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="6c420-110">Se il file app.config contiene già l'elemento `AppContextSwitchOverrides` , il nuovo valore deve essere unito con l'attributo `value` come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6c420-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c420-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c420-111">See also</span></span>

- [<span data-ttu-id="6c420-112">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="6c420-112">Application compatibility</span></span>](application-compatibility.md)
