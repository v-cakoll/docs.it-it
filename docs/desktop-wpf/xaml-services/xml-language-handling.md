---
title: Gestione di xml:lang in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071444"
---
# <a name="xmllang-handling-in-xaml"></a>Gestione di xml:lang in XAML

L'attributo `xml:lang` è un attributo definito in XML che dichiara le informazioni sulla lingua e sulle impostazioni cultura per un elemento in XML. Il significato dell'attributo rimane persistente in XAML. Tuttavia, sono valide alcune considerazioni aggiuntive.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*rfc3066lang*|Stringa derivata dallo standard [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) che identifica una lingua o un'area linguistica. Se identifica un'area linguistica, la lingua e l'area sono separate da un trattino. Per altre informazioni su valori e formato, vedere <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Osservazioni

La definizione `xml:lang` per [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] l'attributo in deriva da `xml:lang` come definito come "attributo speciale" dal World Wide Web Consortium (W3C) per XML. Le informazioni su lingua e cultura sono potenzialmente elaborate in modi diversi in base agli elementi, a seconda delle relative implementazioni. Tuttavia, non esiste alcuna elaborazione [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predefinita dell'attributo `xml:lang` .

Il valore predefinito dell'attributo `xml:lang` è una stringa vuota a livello di attributo.

Gli effetti e il valore dell'attributo `xml:lang` vengono in genere trasferiti agli elementi figlio, quando vengono interpretati da sistemi che usano i valori `xml:lang` .

Quando interpretato dai writer XAML dei `xml:lang` servizi <xref:System.Windows.Markup.XmlLanguage> XAML <xref:System.Globalization.CultureInfo> .NET, un valore può creare o oggetti nella rappresentazione dell'oggetto sottostante; Tuttavia, tale comportamento dipende dal `xml:lang` fatto che il valore specificato per sia una costruzione valida per tali classi.

I framework possono creare associazioni tra le proprietà definite dal framework e il significato di `xml:lang` in XML mediante l'applicazione di <xref:System.Windows.Markup.XmlLangPropertyAttribute> alla proprietà.

## <a name="wpf-usage-nodes"></a>Nodi di uso di WPF

Per gli elementi che sono classi derivate di <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, è possibile usare l'equivalente proprietà di dipendenza <xref:System.Windows.FrameworkElement.Language%2A> anziché l'attributo `xml:lang` . Per impostazione predefinita, la proprietà <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" se non viene specificato un valore diverso tramite la proprietà o tramite l'elaborazione dell'attributo `xml:lang` .

## <a name="see-also"></a>Vedere anche

- [Globalizzazione per WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
