---
title: Direttiva x:ClassModifier
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a>Direttiva x:ClassModifier
Modifica il comportamento di compilazione XAML quando `x:Class` viene inoltre fornita. In particolare, anziché creare un elemento parziale `class` che ha un `Public` (impostazione predefinita), livello di accesso fornito `x:Class` viene creato con un `NotPublic` livello di accesso. Questo comportamento influenza il livello di accesso per la classe nell'assembly generati.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|*NotPublic*|La stringa esatta da passare per specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varia a seconda del linguaggio di programmazione codice in uso. Vedere la sezione Osservazioni.|  
  
## <a name="dependencies"></a>Dipendenze  
 [X:Class](../../../docs/framework/xaml-services/x-class-directive.md) deve inoltre essere disponibile nello stesso elemento, e tale elemento deve essere l'elemento radice in una pagina. Per ulteriori informazioni, vedere [ \[MS-XAML\] sezione 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Note  
 Il valore di `x:ClassModifier` nei servizi XAML di .NET Framework utilizzo varia in base al linguaggio di programmazione. La stringa da utilizzare dipende dal modo in cui ogni linguaggio implementa relativo <xref:System.CodeDom.Compiler.CodeDomProvider> e i convertitori di tipi restituiti per definire il significato per <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> e <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, e se tale lingua viene fatta distinzione tra maiuscole e minuscole.  
  
-   Per [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la stringa da passare per definire <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `internal`.  
  
-   Per [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la stringa da passare per definire <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> è `Friend`.  
  
-   Per [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], nessuna destinazione esistono che supportano la compilazione di XAML; pertanto, non è specificato il valore da passare.  
  
 È inoltre possibile specificare <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); tuttavia, specificando <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> avviene raramente perché <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> è già il comportamento predefinito.  
  
 Altri valori con il codice utente equivalente a livello di accesso restrizioni, ad esempio `private` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], non sono rilevanti per `x:ClassModifier` perché i riferimenti a classi annidate non sono supportati in XAML e di conseguenza, il <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificatore ha lo stesso effetto.  
  
## <a name="security-notes"></a>Note sulla sicurezza  
 Il livello di accesso, come dichiarato in `x:ClassModifier` viene interpretato ancora determinati Framework e le relative funzionalità. WPF include funzionalità per caricare e creare istanze di tipi in cui `x:ClassModifier` è `internal`, se tale classe viene fatto riferimento da una risorsa WPF tramite un riferimento all'URI di tipo pack. Di conseguenza questo caso e potenzialmente di altri utenti, quali quelle implementate da altri Framework, non fare affidamento esclusivamente su `x:ClassModifier` tenta di bloccare la creazione di istanze di tutti i possibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Code-behind e XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Direttiva x:FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Sicurezza (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [Tipi migrati da WPF a System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
