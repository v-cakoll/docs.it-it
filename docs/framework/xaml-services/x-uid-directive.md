---
title: Direttiva x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 32cfd9ab0cf6037c731b619e81a7504ac92d5fb9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837181"
---
# <a name="xuid-directive"></a>Direttiva x:Uid
Fornisce un identificatore univoco per gli elementi di markup. In molti scenari, questo identificatore univoco viene usato dai processi e dagli strumenti di localizzazione XAML.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`identifier`|Stringa creata manualmente o generata automaticamente che deve essere univoca in un file quando viene interpretata da un consumer `x:Uid`.|  
  
## <a name="remarks"></a>Note  
 In [MS-XAML] `x:Uid` viene definito come direttiva. Per ulteriori informazioni, vedere la [sezione\[MS-XAML\] 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 `x:Uid` è discreto rispetto a `x:Name` a causa dello scenario di localizzazione XAML indicato e, pertanto, gli identificatori utilizzati per la localizzazione non hanno dipendenze dalle implicazioni del modello di programmazione di `x:Name`. Inoltre, `x:Name` è governato dall'ambito dei nomi XAML. Tuttavia, `x:Uid` non è regolata da alcun concetto di imposizione di univocità definito dal linguaggio XAML. I processori XAML in senso ampio (i processori che non fanno parte del processo di localizzazione) non sono previsti per applicare l'univocità dei valori `x:Uid`. Questa responsabilità è concettualmente sul creatore dei valori. La previsione di univocità dei valori `x:Uid` all'interno di una singola origine XAML è ragionevole per i consumer dei valori, ad esempio processi di globalizzazione dedicati o strumenti. Il modello di univocità tipico è che i valori `x:Uid` sono univoci all'interno di un file con codifica XML che rappresenta XAML.  
  
 Gli strumenti con una conoscenza significativa di uno schema XAML specifico possono scegliere di applicare `x:Uid` solo per le stringhe localizzabili vere, anziché per tutti i casi in cui viene rilevato un valore stringa di testo nel markup.  
  
 I Framework possono specificare una particolare proprietà nel modello a oggetti per essere un alias per `x:Uid` applicando l'attributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo di definizione. Se un Framework specifica una particolare proprietà, non è possibile specificare sia `x:Uid` che il membro con alias nello stesso oggetto. Se vengono specificati sia `x:Uid` che il membro con alias, l'API dei servizi XAML .NET Framework genera in genere <xref:System.Xaml.XamlDuplicateMemberException> in questo caso.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Per ulteriori informazioni sul ruolo di `x:Uid` nel processo di localizzazione WPF e nella forma BAML di XAML, vedere [globalizzazione per WPF](../wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalizzazione per WPF](../wpf/advanced/globalization-for-wpf.md)
