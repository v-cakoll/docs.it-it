---
title: Direttiva x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 7075f8258e617d2d13d4585fdd5fb7aefaa50664
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452629"
---
# <a name="xuid-directive"></a>Direttiva x:Uid
Fornisce un identificatore univoco per gli elementi di markup. In molti scenari, questo identificatore univoco viene usato dai processi di localizzazione XAML e dagli strumenti.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`identifier`|Creata manualmente o stringa generata automaticamente che deve essere univoco in un file quando viene interpretata da un `x:Uid` consumer.|  
  
## <a name="remarks"></a>Note  
 In [MS-XAML], `x:Uid` viene definito come una direttiva. Per altre informazioni, vedere [ \[MS-XAML\] sezione 5.3.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` è discrete e provengono dalle `x:Name` entrambi a causa dello scenario dichiarato localizzazione XAML e in modo che gli identificatori utilizzati per la localizzazione non hanno dipendenze sulle implicazioni del modello di programmazione di `x:Name`. È inoltre `x:Name` è disciplinato dal namescope XAML; tuttavia, `x:Uid` non è governato da nessun concetto di linguaggio definito XAML di imposizione di univocità. Processori XAML in una prospettiva ampliata (processori che non fanno parte del processo di localizzazione) non possono imporre l'univocità di `x:Uid` valori. Tale compito è concettualmente il creatore dei valori. L'aspettativa di univocità di `x:Uid` valori all'interno di una singola fonte XAML a diminuire è ragionevole per i consumer dei valori, ad esempio strumenti o processi di globalizzazione dedicato. Il modello di univocità tipica è che `x:Uid` valori siano univoci all'interno di un file con codifica XML che rappresenta il XAML.  
  
 Gli strumenti che hanno notevoli conoscenze di un determinato schema XAML è possono scegliere di applicare `x:Uid` solo per true stringhe localizzabili, anziché per tutti i casi in cui viene rilevato un valore di stringa di testo nel markup.  
  
 Framework è possono specificare una determinata proprietà nel modello a oggetti sia un alias per `x:Uid` applicando l'attributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo di definizione. Se un framework specifica una particolare proprietà, non è consentito specificare le `x:Uid` e il membro con alias nello stesso oggetto. Se entrambe `x:Uid` e il membro con alias vengono specificati, l'API di servizi XAML di .NET Framework genera un'eccezione in genere <xref:System.Xaml.XamlDuplicateMemberException> per questo case.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Per altre informazioni sul ruolo degli `x:Uid` nel processo di localizzazione WPF e nel modulo BAML di XAML, vedere [globalizzazione per WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [Globalizzazione per WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
