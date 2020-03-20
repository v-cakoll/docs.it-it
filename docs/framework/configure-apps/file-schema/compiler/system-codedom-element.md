---
title: Elemento <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155388"
---
# <a name="systemcodedom-element"></a>\<system.codedom>elemento
Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;**\<>system.codedom**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<compilatori>](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero [ \<](compiler-element.md) o più elementi>del compilatore.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di configurazione](../configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="net-framework-version-20"></a>.NET Framework versione 2.0  
 L'elemento [ \<system.codedom>](system-codedom-element.md) contiene le impostazioni di configurazione del compilatore per i provider del linguaggio <xref:Microsoft.CSharp.CSharpCodeProvider> installati <xref:Microsoft.VisualBasic.VBCodeProvider>in un computer oltre ai provider predefiniti installati con .NET Framework, ad esempio e . L'elemento [ \<>compilatori](compilers-element.md) contiene zero o più [ \<elementi>compilatore.](compiler-element.md) Ogni elemento [ \<>del compilatore](compiler-element.md) specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.  
  
 Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni <xref:System.CodeDom.Compiler.CodeDomProvider> di configurazione al file di configurazione del computer (Machine.config) per una nuova implementazione. Utilizzare <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> il metodo per enumerare a livello di codice sia i provider di linguaggio predefiniti che i provider di linguaggio identificati dalle impostazioni di configurazione del compilatore in un computer.  
  
> [!NOTE]
> In .NET Framework versioni 1.0 e 1.1 i provider di linguaggi predefiniti forniti da .NET Framework vengono identificati nell'elemento [ \<>compilatori.](compilers-element.md) In .NET Framework versione 2.0 i provider di linguaggi predefiniti non sono identificati nell'elemento <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> [ \<>compilatori,](compilers-element.md) ma possono essere enumerati utilizzando il metodo .  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework versioni 1.0 e 1.1  
 L'elemento [ \<system.codedom>](system-codedom-element.md) contiene le impostazioni di configurazione del compilatore per i provider di linguaggiinun computer. L'elemento [ \<>compilatori](compilers-element.md) contiene zero o più [ \<elementi>compilatore.](compiler-element.md) Ogni elemento [ \<>del compilatore](compiler-element.md) specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.  
  
 .NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una configurazione tipica del compilatore.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema del file di configurazione](../index.md)
- [Schema delle impostazioni del compilatore e del provider di linguaggioCompiler and Language Provider Settings Schema](index.md)
- [\<> del compilatore](compiler-element.md)
