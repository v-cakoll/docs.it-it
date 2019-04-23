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
ms.openlocfilehash: fdbc69634e86992e71cfccdc080829b6b45f963c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100927"
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier
Modifica il comportamento di compilazione XAML quando `x:Class` viene anche fornito. In particolare, invece di creare un elemento parziale `class` che ha un `Public` (impostazione predefinita), livello di accesso fornito `x:Class` viene creato con un `NotPublic` livello di accesso. Questo comportamento influisce sul livello di accesso per la classe nell'assembly generati.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*NotPublic*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> rispetto a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione di code-behind in uso. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 [X:Class](x-class-directive.md) deve anche essere specificato per lo stesso elemento, e tale elemento deve essere l'elemento radice in una pagina. Per altre informazioni, vedere [ \[MS-XAML\] sezione 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il valore di `x:ClassModifier` nei servizi XAML di .NET Framework utilizzo varia in base al linguaggio di programmazione. La stringa da usare dipende dal modo in cui ogni linguaggio implementa relativi <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire gli stessi significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua è distinzione maiuscole / minuscole.  
  
-   Per c#, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.  
  
-   Per Microsoft Visual Basic .NET, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.  
  
-   Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nessuna destinazione esistono che supportano la compilazione XAML; pertanto, non è specificato il valore da passare.  
  
 È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in c# `Public` in Visual Basic); tuttavia, specificando <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> avviene raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> corrisponde già al comportamento predefinito.  
  
 Altri valori con il codice utente equivalenti a livello di accesso restrizioni, ad esempio `private` in c#, non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e di conseguenza, il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificatore ha lo stesso effetto.  
  
## <a name="security-notes"></a>Note sulla sicurezza  
 Il livello di accesso come dichiarato in `x:ClassModifier` è ancora soggetta a interpretazioni da determinati Framework e le relative funzionalità. WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal`, se tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack. Di conseguenza questo caso e potenzialmente di altri utenti, ad esempio viene implementato da altri Framework, non fare affidamento esclusivamente su `x:ClassModifier` per bloccare la creazione di istanze di tutti i possibili tentativi.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:FieldModifier](x-fieldmodifier-directive.md)
- [Security (WPF)](../wpf/security-wpf.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
