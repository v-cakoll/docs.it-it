---
title: Direttiva x:FieldModifier
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 27ff9d027f5ff5155543097b7f0f0c2839387fe5
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58042447"
---
# <a name="xfieldmodifier-directive"></a>Direttiva x:FieldModifier
È possibile modificare il comportamento di compilazione XAML in modo che i campi per i riferimenti agli oggetti denominati sono definiti con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> accesso anziché il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> il comportamento predefinito.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*Public*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> rispetto a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione di code-behind che viene usato. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 Se viene utilizzata una produzione XAML `x:FieldModifier` ovunque, l'elemento radice di tale ambiente di produzione XAML è necessario dichiarare un' [direttiva X:Class](x-class-directive.md).  
  
## <a name="remarks"></a>Note  
 `x:FieldModifier` non è rilevante per la dichiarazione del livello di accesso generale di una classe o i relativi membri. È rilevante solo per l'elaborazione di XAML comportamento quando un determinato oggetto XAML che fa parte di una produzione XAML viene elaborato e diventa un oggetto che è potenzialmente accessibile nell'oggetto grafico di un'applicazione. Per impostazione predefinita, il riferimento di campo per tale tipo di oggetto è privato, che impedisce ai consumer dei controlli di modifica direttamente l'oggetto grafico. Al contrario, i consumer di controllo dovrebbero modificare il grafico di oggetti dall'utilizzo di modelli standard che sono abilitati per i modelli di programmazione, ad esempio ottenendo la radice di layout, l'elemento figlio di raccolte di elementi, le proprietà pubbliche dedicate, e così via.  
  
 Il valore per il `x:FieldModifier` attributo varia in base al linguaggio di programmazione e framework specifici può variare il suo scopo. La stringa da usare dipende dal modo in cui ogni linguaggio implementa relativi <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire gli stessi significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua è distinzione maiuscole / minuscole.  
  
-   Per C#, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `public`.  
  
-   Per Microsoft Visual Basic .NET, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `Public`.  
  
-   Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], non esistono attualmente alcuna destinazione per XAML, pertanto la stringa da passare è indefinita.  
  
 È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) ma la specifica <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> insolita perché `NotPublic` come il comportamento è già il valore predefinito.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è il comportamento predefinito, in quanto è insolito che codice esterno all'assembly compilato il XAML deve accedere a un elemento XAML-creato. Architettura di sicurezza WPF con il comportamento di compilazione XAML non vengono dichiarati i campi che archiviano le istanze dell'elemento come pubblico, a meno che non si imposti la `x:FieldModifier` per consentire l'accesso pubblico.  
  
 `x:FieldModifier` è rilevante solo per gli elementi con un [direttiva X:Name](x-name-directive.md) perché tale nome viene usato per fare riferimento al campo dopo che è pubblico.  
  
 Per impostazione predefinita, la classe parziale per l'elemento radice è pubblica; Tuttavia, è possibile renderlo non pubblici tramite il [direttiva X:ClassModifier](x-classmodifier-directive.md). Il [direttiva X:ClassModifier](x-classmodifier-directive.md) interesserà anche il livello di accesso dell'istanza della classe dell'elemento radice. È possibile inserire entrambe `x:Name` e `x:FieldModifier` nella radice del solo elemento, ma questo crea una copia di campo pubblico dell'elemento radice, con il principale effettiva classe accesso livello elemento ancora controllata da [direttiva X:ClassModifier](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Vedere anche
- [Classi XAML e personalizzate per WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:Name](x-name-directive.md)
- [Compilazione di un'applicazione WPF (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)
- [Direttiva x:ClassModifier](x-classmodifier-directive.md)
