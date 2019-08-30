---
title: Schema di impostazioni del compilatore e del provider di linguaggi
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: a651e4ca76fda9e65ea4a5848c19b1f0ebfe91b1
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168934"
---
# <a name="compiler-and-language-provider-settings-schema"></a>Schema di impostazioni del compilatore e del provider di linguaggi
Le impostazioni del compilatore e del provider di linguaggi specificano gli elementi di configurazione del compilatore per i provider di linguaggi disponibili. Ogni elemento di configurazione del compilatore specifica il nome del tipo di provider di codice, i parametri del compilatore, i nomi dei linguaggi supportati e le estensioni di file supportate.  
  
.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<> System. CodeDom**](system-codedom-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<compilatori >** ](compilers-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del compilatore**](compiler-element.md)  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.codedom>](system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<compilers>](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](compiler-element.md).|  
|[\<compiler>](compiler-element.md)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un elemento di configurazione del compilatore tipico.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema dei file di configurazione](../index.md)
- [\<compiler> Element](compiler-element.md) (Elemento <compiler>)
