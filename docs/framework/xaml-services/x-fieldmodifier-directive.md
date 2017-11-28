---
title: Direttiva x:FieldModifier
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 77745744c0da1e4b4425af6d8e4319faaf524908
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xfieldmodifier-directive"></a>Direttiva x:FieldModifier
È possibile modificare il comportamento di compilazione XAML in modo che i campi per riferimenti a oggetti denominati definiti con <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> accesso anziché il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> il comportamento predefinito.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per gli attributi  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*Public*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione codice che viene utilizzato. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 Se viene utilizzata una produzione XAML `x:FieldModifier` in qualsiasi punto, è necessario dichiarare l'elemento radice di quella produzione XAML un [direttiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## <a name="remarks"></a>Note  
 `x:FieldModifier`non è pertinente per dichiarare il livello di accesso generale di una classe o i relativi membri. È rilevante solo per il comportamento di elaborazione XAML quando un determinato oggetto XAML che fa parte di una produzione XAML viene elaborato e diventa un oggetto potenzialmente accessibile nell'oggetto grafico di un'applicazione. Per impostazione predefinita, il riferimento di campo per tale oggetto è privato, che impedisce ai consumer dei controlli di modifica diretta di un oggetto grafico. Al contrario, i consumer di controllo dovrebbero modificare l'oggetto grafico utilizzando i modelli standard che sono abilitati per i modelli di programmazione, ad esempio ottenendo la radice di layout, l'elemento figlio, le raccolte di elementi, le proprietà pubbliche dedicate, e così via.  
  
 Il valore per il `x:FieldModifier` attributo varia in base al linguaggio di programmazione e il suo scopo può variare in Framework specifici. La stringa da utilizzare dipende dal modo in cui ogni linguaggio implementa relativo <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire il significato per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua viene fatta distinzione tra maiuscole e minuscole.  
  
-   Per [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la stringa da passare per definire <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `public`.  
  
-   Per [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la stringa da passare per definire <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è `Public`.  
  
-   Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nessuna destinazione disponibile per il codice XAML attualmente esistono, pertanto non è definita la stringa da passare.  
  
 È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]) ma la specifica <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è insolito perché `NotPublic` il comportamento è già il valore predefinito.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>è il comportamento predefinito, in quanto è insolito che codice esterno all'assembly compilato il codice XAML deve accedere a un elemento creato XAML. Architettura di sicurezza WPF con il comportamento di compilazione XAML non vengono dichiarati i campi che memorizzano le istanze dell'elemento come pubblici, a meno che non si imposti il `x:FieldModifier` per consentire l'accesso pubblico.  
  
 `x:FieldModifier`è importante solo per gli elementi con un [direttiva X:Name](../../../docs/framework/xaml-services/x-name-directive.md) perché tale nome viene utilizzato per fare riferimento al campo dopo che è pubblico.  
  
 Per impostazione predefinita, la classe parziale per l'elemento radice è pubblica. Tuttavia, è possibile renderlo non pubblici tramite il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md). Il [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md) interesserà anche il livello di accesso dell'istanza di classe dell'elemento radice. È possibile inserire `x:Name` e `x:FieldModifier` nella radice solo elemento, ma questo crea una copia di campo pubblico dell'elemento radice, con il livello vero elemento radice classe accesso ancora controllata da [direttiva X:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Code-behind e XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Direttiva x:Name](../../../docs/framework/xaml-services/x-name-directive.md)  
 [Compilazione di un'applicazione WPF (WPF)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Direttiva x:ClassModifier](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
