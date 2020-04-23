---
title: Direttiva x:ClassModifier
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072032"
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier
Modifica il comportamento di `x:Class` compilazione XAML quando viene fornito anche. In particolare, anziché `class` creare `Public` un partial con un `x:Class` livello di `NotPublic` accesso (impostazione predefinita), l'oggetto fornito viene creato con un livello di accesso. Questo comportamento influisce sul livello di accesso per la classe negli assembly generati.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*NotPublic (NotPubblico)*|La stringa esatta da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> passare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> da specificare rispetto a varia a seconda del linguaggio di programmazione code-behind utilizzato. Vedere la sezione Osservazioni.|

## <a name="dependencies"></a>Dependencies

[x:Class](xclass-directive.md) deve essere fornito anche sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina.x:Class must also be provided on the same element, and that element must be the root element in a page. Per ulteriori informazioni, vedere [ \[Sezione MS-XAML\] 4.3.1.8.](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

## <a name="remarks"></a>Osservazioni

Il valore `x:ClassModifier` di in .NET XAML Services usage varia in base al linguaggio di programmazione. La stringa da utilizzare dipende dal <xref:System.CodeDom.Compiler.CodeDomProvider> modo in cui ogni linguaggio implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>i convertitori di tipo che restituisce per definire i significati per e e se tale lingua fa distinzione tra maiuscole e minuscole.

- Per il linguaggio C, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> la `internal`stringa da passare a designate è .

- Per Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`stringa da passare a designate è .

- Per c'è/CLI, non esistono destinazioni che supportano la compilazione di XAML. pertanto, il valore da passare non è specificato.

È anche <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> possibile`public` specificare `Public` ( in C, in Visual Basic); Tuttavia, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> la specifica viene <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> eseguita raramente perché è già il comportamento predefinito.

Altri valori con restrizioni equivalenti a livello `private` di accesso al codice `x:ClassModifier` utente, ad esempio in C, non <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> sono rilevanti perché i riferimenti alle classi annidate non sono supportati in XAML e pertanto il modificatore ha lo stesso effetto.

## <a name="security-notes"></a>Note sulla sicurezza

Il livello di `x:ClassModifier` accesso dichiarato in è ancora soggetto a interpretazione da parte di particolari quadri e delle loro capacità. WPFWPF include funzionalità per `x:ClassModifier` caricare `internal`e creare istanze di tipi dove è , se tale classe fa riferimento da una risorsa WPFwpf tramite un riferimento URI di tipo pack. Come conseguenza di questo caso e potenzialmente altri simili implementati da `x:ClassModifier` altri framework, non si basano esclusivamente su per bloccare tutti i possibili tentativi di creazione di istanze.

## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](xclass-directive.md)
- [Code-behind e XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:FieldModifier](xfieldmodifier-directive.md)
- [Sicurezza (WPF)](../../framework/wpf/security-wpf.md)
- [Tipi migrati da WPF a System.Xaml](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
