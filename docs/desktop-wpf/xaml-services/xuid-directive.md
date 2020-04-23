---
title: Direttiva x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071339"
---
# <a name="xuid-directive"></a>Direttiva x:Uid

Fornisce un identificatore univoco per gli elementi di markup. In molti scenari, questo identificatore univoco viene usato dai processi e dagli strumenti di localizzazione XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`identifier`|Stringa creata manualmente o generata automaticamente che deve essere univoca in un file quando viene interpretata da un `x:Uid` consumer.|

## <a name="remarks"></a>Osservazioni

In [MS-XAML], `x:Uid` è definito come una direttiva. Per ulteriori informazioni, vedere [ \[la sezione MS-XAML\] 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid`è discreto `x:Name` sia per lo scenario di localizzazione XAML dichiarato che per tanto che gli identificatori `x:Name`utilizzati per la localizzazione non hanno dipendenze dalle implicazioni del modello di programmazione di . Inoltre, `x:Name` è governato dall'ambito dei nomi XAML; Tuttavia, `x:Uid` non è regolato da alcun concetto definito dal linguaggio XAML di imposizione dell'univocità. I processori XAML in senso lato (processori che non fanno parte del `x:Uid` processo di localizzazione) non devono applicare l'univocità dei valori. Tale responsabilità è concettualmente sull'originatore dei valori. L'aspettativa di `x:Uid` unicità dei valori all'interno di una singola origine XAML è ragionevole per i consumer dei valori, ad esempio strumenti o processi di globalizzazione dedicati. Il modello di unicità tipico è che `x:Uid` i valori sono univoci all'interno di un file con codifica XML che rappresenta XAML.

Gli strumenti che hanno una conoscenza significativa `x:Uid` di un particolare schema XAML possono scegliere di applicare solo per le stringhe localizzabili true, anziché per tutti i casi in cui viene rilevato un valore di stringa di testo nel markup.

I framework possono specificare una particolare proprietà nel `x:Uid` proprio modello <xref:System.Windows.Markup.UidPropertyAttribute> a oggetti per cui essere un alias applicando l'attributo al tipo di definizione. Se un framework specifica una determinata proprietà, `x:Uid` non è valido specificare entrambi e il membro con alias sullo stesso oggetto. Se `x:Uid` vengono specificati entrambi e il membro con alias, <xref:System.Xaml.XamlDuplicateMemberException> l'API dei servizi XAML .NET genera in genere un'eccezione per questo caso.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Per altre informazioni sul `x:Uid` ruolo del processo di localizzazione WPF e nel formato BAML di XAML, vedere [Globalizzazione per WPF](../../framework/wpf/advanced/globalization-for-wpf.md) o<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalizzazione per WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
