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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837233"
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier
Modifica il comportamento di compilazione XAML quando viene fornito anche `x:Class`. In particolare, anziché creare un `class` parziale con un livello di accesso `Public` (impostazione predefinita), il `x:Class` fornito viene creato con un livello di accesso `NotPublic`. Questo comportamento influiscono sul livello di accesso per la classe negli assembly generati.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|*NotPublic*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> rispetto a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione code-behind usato. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 è necessario fornire anche [x:Class](x-class-directive.md) sullo stesso elemento e tale elemento deve essere l'elemento radice in una pagina. Per ulteriori informazioni, vedere la [sezione\[MS-XAML\] 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Note  
 Il valore di `x:ClassModifier` in .NET Framework uso dei servizi XAML varia in base al linguaggio di programmazione. La stringa da usare dipende dal modo in cui ogni linguaggio implementa la <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire i significati per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>e se tale lingua fa distinzione tra maiuscole e minuscole.  
  
- Per C#, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.  
  
- Per Microsoft Visual Basic .NET, la stringa da passare per designare <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.  
  
- Per C++/CLI non esistono destinazioni che supportano la compilazione di XAML. Pertanto, il valore da passare non è specificato.  
  
 È anche possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); Tuttavia, la specifica di <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> viene eseguita raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è già il comportamento predefinito.  
  
 Altri valori con restrizioni a livello di accesso del codice utente equivalente, ad esempio C#`private` in, non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e pertanto il modificatore di <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ha lo stesso effetto.  
  
## <a name="security-notes"></a>Note sulla sicurezza  
 Il livello di accesso dichiarato nel `x:ClassModifier` è ancora soggetto all'interpretazione da parte di Framework particolari e delle relative funzionalità. WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal`, se a tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento URI di tipo pack. Come conseguenza di questo caso e potenzialmente altri come implementato da altri Framework, non si basano esclusivamente su `x:ClassModifier` per bloccare tutti i possibili tentativi di creazione di istanze.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Direttiva x:FieldModifier](x-fieldmodifier-directive.md)
- [Sicurezza (WPF)](../wpf/security-wpf.md)
- [Tipi migrati da WPF a System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
