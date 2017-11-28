---
title: Direttiva x:Uid
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 4d49e9630b481b2daf103feabd225dd5ef0c8ca2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xuid-directive"></a>Direttiva x:Uid
Fornisce un identificatore univoco per gli elementi di markup. In molti scenari, questo identificatore univoco viene utilizzato dagli strumenti e processi di localizzazione XAML.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per gli attributi  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`identifier`|Creata manualmente o stringa generata automaticamente che deve essere univoco in un file quando viene interpretato da un `x:Uid` consumer.|  
  
## <a name="remarks"></a>Note  
 In [MS-XAML], `x:Uid` è definito come una direttiva. Per ulteriori informazioni, vedere [ \[MS-XAML\] sezione 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid`viene discreti da `x:Name` entrambi a causa dello scenario di localizzazione XAML dichiarato e in modo che gli identificatori utilizzati per la localizzazione non hanno dipendenze sulle implicazioni del modello di programmazione di `x:Name`. Inoltre, `x:Name` è disciplinato dalle namescope XAML; tuttavia, `x:Uid` non è governato da qualsiasi linguaggio XAML definito concetto di imposizione di univocità. I processori XAML in una prospettiva ampliata (processori che non fanno parte del processo di localizzazione) non è previsto per imporre l'univocità di `x:Uid` valori. Tale compito è concettualmente del creatore dei valori. La prospettiva di univocità di `x:Uid` valori all'interno di una singola origine XAML, è ragionevole per i consumer dei valori, ad esempio strumenti o processi di globalizzazione dedicati. Il modello di univocità tipica è che `x:Uid` valori siano univoci all'interno di un file con codifica XML che rappresenta il XAML.  
  
 Strumenti che dispongono di conoscenza significativa di un particolare schema XAML è possono scegliere di applicare `x:Uid` solo per true stringhe localizzabili, anziché per tutti i casi in cui viene rilevato un valore di stringa di testo nel markup.  
  
 Framework è possono specificare una determinata proprietà nel modello a oggetti come alias per `x:Uid` applicando l'attributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo di definizione. Se un framework specifica una proprietà specifica, non è consentito specificare sia `x:Uid` e il membro con alias sullo stesso oggetto. Se entrambi `x:Uid` e vengono specificati il membro con alias, l'API dei servizi XAML di .NET Framework genera di solito <xref:System.Xaml.XamlDuplicateMemberException> in questo caso.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Per ulteriori informazioni sul ruolo degli `x:Uid` nel processo di localizzazione WPF e il modulo BAML di XAML, vedere [globalizzazione per WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) o<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [Globalizzazione per WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
