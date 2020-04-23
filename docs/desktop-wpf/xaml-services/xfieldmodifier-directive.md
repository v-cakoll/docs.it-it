---
title: Direttiva x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071528"
---
# <a name="xfieldmodifier-directive"></a>Direttiva x:FieldModifier
Modifica il comportamento di compilazione XAML in modo <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> che i <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> campi per i riferimenti a oggetti denominati vengano definiti con accesso anziché con il comportamento predefinito.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|*Pubblica*|La stringa esatta passata da specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> rispetto a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione code-behind utilizzato. Vedere la sezione Osservazioni.|

## <a name="dependencies"></a>Dependencies

 Se una produzione `x:FieldModifier` XAML usa in qualsiasi punto, l'elemento radice di tale produzione XAML deve dichiarare [una direttiva x:Class](xclass-directive.md).

## <a name="remarks"></a>Osservazioni

`x:FieldModifier`non è rilevante per dichiarare il livello di accesso generale di una classe o dei relativi membri. È rilevante solo per il comportamento di elaborazione XAML quando viene elaborato un particolare oggetto XAML che fa parte di una produzione XAML e diventa un oggetto potenzialmente accessibile nell'oggetto grafico di un'applicazione. Per impostazione predefinita, il riferimento al campo per un oggetto di questo tipo viene mantenuto privato, impedendo ai consumer di controlli di modificare direttamente l'oggetto grafico. Al contrario, i consumer di controlli devono modificare l'oggetto grafico utilizzando modelli standard abilitati dai modelli di programmazione, ad esempio ottenendo la radice del layout, le raccolte di elementi figlio, le proprietà pubbliche dedicate e così via.

Il valore `x:FieldModifier` dell'attributo varia in base al linguaggio di programmazione e il relativo scopo può variare in framework specifici. La stringa da utilizzare dipende dal <xref:System.CodeDom.Compiler.CodeDomProvider> modo in cui ogni linguaggio implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>i convertitori di tipo che restituisce per definire i significati per e e se tale lingua fa distinzione tra maiuscole e minuscole.

- Per il linguaggio C, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> la `public`stringa da passare a designate è .

- Per Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`stringa da passare a designate è .

- Per il linguaggio C, non esistono attualmente destinazioni per XAML. pertanto, la stringa da passare non è definita.

È anche <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> possibile`internal` specificare `Friend` ( in C , <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> in `NotPublic` Visual Basic), ma specificare è insolito perché il comportamento è già l'impostazione predefinita.

<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>è il comportamento predefinito perché non è frequente che il codice all'esterno dell'assembly che ha compilato il codice XAML deve accedere a un elemento creato da XAML. L'architettura di sicurezza WPF con il comportamento di compilazione XAML non `x:FieldModifier` dichiarerà i campi che archiviano le istanze degli elementi come pubbliche, a meno che non si imposti in modo specifico l'oggetto per consentire l'accesso pubblico.

`x:FieldModifier`è rilevante solo per gli elementi con una [direttiva x:Name](xname-directive.md) perché tale nome viene utilizzato per fare riferimento al campo dopo che è pubblico.

Per impostazione predefinita, la classe parziale per l'elemento radice è pubblica; Tuttavia, è possibile renderlo non pubblico utilizzando la [direttiva x:ClassModifier](xclassmodifier-directive.md). La [direttiva x:ClassModifier](xclassmodifier-directive.md) influisce anche sul livello di accesso dell'istanza della classe dell'elemento radice. È possibile `x:Name` inserire `x:FieldModifier` entrambi e sull'elemento radice , ma in questo modo viene creata solo una copia di campo pubblica dell'elemento radice, con il vero livello di accesso alla classe dell'elemento radice ancora controllato dalla [direttiva x:ClassModifier](xclassmodifier-directive.md).

## <a name="see-also"></a>Vedere anche

- [Classi XAML e personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-behind e XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:Name](xname-directive.md)
- [Compilazione di un'applicazione WPF (WPF)Building a WPF Application (WPF)](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [Direttiva x:ClassModifier](xclassmodifier-directive.md)
