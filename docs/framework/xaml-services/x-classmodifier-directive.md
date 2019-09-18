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
ms.openlocfilehash: 5daff0567c1b1415fe994f6e39b4079cb2ab7346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053823"
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier
Modifica il comportamento di compilazione `x:Class` XAML quando viene fornito anche. In particolare, anziché creare un oggetto `class` parziale `Public` con livello di accesso (impostazione predefinita), l'oggetto `x:Class` fornito viene creato con `NotPublic` un livello di accesso. Questo comportamento influiscono sul livello di accesso per la classe negli assembly generati.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*NotPublic*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e varia a seconda del linguaggio di programmazione code-behind usato. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 è necessario fornire anche [x:Class](x-class-directive.md) sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina. Per ulteriori informazioni, vedere [ \[la sezione MS\] -XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il valore di `x:ClassModifier` in .NET Framework uso dei servizi XAML varia in base al linguaggio di programmazione. La stringa da usare dipende dal modo in cui ogni linguaggio implementa <xref:System.CodeDom.Compiler.CodeDomProvider> i convertitori di tipi che restituisce per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>e se tale lingua fa distinzione tra maiuscole e minuscole.  
  
- Per C#, la stringa da passare a designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.  
  
- Per Microsoft Visual Basic .NET, la stringa da passare a designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.  
  
- Per C++/CLI non esistono destinazioni che supportano la compilazione di XAML. Pertanto, il valore da passare non è specificato.  
  
 È anche possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic). Tuttavia, l' <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> impostazione di viene eseguita raramente <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> perché è già il comportamento predefinito.  
  
 Altri valori con restrizioni a livello di accesso del codice utente equivalente, `private` ad C#esempio in, non sono `x:ClassModifier` rilevanti per perché i riferimenti a classi annidate non sono supportati in XAML <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> e pertanto il modificatore ha lo stesso effetto .  
  
## <a name="security-notes"></a>Note sulla sicurezza  
 Il livello di accesso dichiarato in `x:ClassModifier` è ancora soggetto all'interpretazione da parte di framework specifici e alle relative funzionalità. WPF include funzionalità per caricare e creare istanze di tipi `x:ClassModifier` in `internal`cui è, se a tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack. Come conseguenza di questo caso e potenzialmente altri come implementati da altri Framework, non si basano esclusivamente su `x:ClassModifier` per bloccare tutti i possibili tentativi di creazione di istanze.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:FieldModifier](x-fieldmodifier-directive.md)
- [Sicurezza (WPF)](../wpf/security-wpf.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
