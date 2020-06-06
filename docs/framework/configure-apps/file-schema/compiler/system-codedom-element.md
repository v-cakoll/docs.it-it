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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155388"
---
# <a name="systemcodedom-element"></a>\<system.codedom> Elemento
Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero o più [\<compiler>](compiler-element.md) elementi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Commenti  
  
## <a name="net-framework-version-20"></a>.NET Framework versione 2,0  
 L' [\<system.codedom>](system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio installati in un computer, oltre ai provider predefiniti installati con il .NET Framework, ad esempio <xref:Microsoft.CSharp.CSharpCodeProvider> e <xref:Microsoft.VisualBasic.VBCodeProvider> . L' [\<compilers>](compilers-element.md) elemento contiene zero o più [\<compiler>](compiler-element.md) elementi. Ogni [\<compiler>](compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.  
  
 Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione al file di configurazione del computer (Machine. config) per una nuova <xref:System.CodeDom.Compiler.CodeDomProvider> implementazione. Usare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di codice sia i provider di lingua predefiniti che i provider di linguaggio identificati dalle impostazioni di configurazione del compilatore in un computer.  
  
> [!NOTE]
> Nelle versioni .NET Framework 1,0 e 1,1, i provider di lingua predefiniti forniti dall'.NET Framework sono identificati nell' [\<compilers>](compilers-element.md) elemento. In .NET Framework versione 2,0 i provider di lingua predefiniti non sono identificati nell' [\<compilers>](compilers-element.md) elemento, ma possono essere enumerati utilizzando il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> metodo.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework versioni 1,0 e 1,1  
 L' [\<system.codedom>](system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggio in un computer. L' [\<compilers>](compilers-element.md) elemento contiene zero o più [\<compiler>](compiler-element.md) elementi. Ogni [\<compiler>](compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico.  
  
 .NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una tipica configurazione del compilatore.  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema del file di configurazione](../index.md)
- [Schema di impostazioni del compilatore e del provider di linguaggi](index.md)
- [\<compiler>Elemento](compiler-element.md)
