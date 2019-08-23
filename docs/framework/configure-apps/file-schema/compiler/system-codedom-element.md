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
ms.openlocfilehash: 43bc3c40bfc0b0ce4c0b18683092faf8b67e1c04
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927700"
---
# <a name="systemcodedom-element"></a>\<Elemento > System. CodeDom
Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.  
  
 \<Configuration >-elemento  
\<Elemento > System. CodeDom  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](compiler-element.md).|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Note  
  
## <a name="net-framework-version-20"></a>.NET Framework versione 2,0  
 <xref:Microsoft.CSharp.CSharpCodeProvider> L' [ \<elemento > System. CodeDom](system-codedom-element.md) contiene le impostazioni di configurazione del compilatore per i provider di linguaggi installati in un computer, oltre ai provider predefiniti installati con il .NET Framework, ad esempio e <xref:Microsoft.VisualBasic.VBCodeProvider>. [ Il\<compilatore >](compilers-element.md) elemento contiene zero o più [ \<elementi > del compilatore](compiler-element.md) . Ogni elemento > del compilatore specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico. [ \<](compiler-element.md)  
  
 Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione al file di configurazione del computer ( <xref:System.CodeDom.Compiler.CodeDomProvider> Machine. config) per una nuova implementazione. Usare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di codice sia i provider di lingua predefiniti che i provider di linguaggio identificati dalle impostazioni di configurazione del compilatore in un computer.  
  
> [!NOTE]
> Nelle versioni .NET Framework 1,0 e 1,1, i provider di lingua predefiniti forniti dall'.NET Framework sono identificati nell' [ \<elemento >](compilers-element.md) compilatori. In .NET Framework versione 2,0 i provider di lingua predefiniti non sono identificati nell' <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> [ \<elemento > compilatori](compilers-element.md) , ma possono essere enumerati utilizzando il metodo.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework versioni 1,0 e 1,1  
 L'elemento > [System. CodeDom contiene le impostazioni di configurazione del compilatore per i provider del linguaggio in un computer. \<](system-codedom-element.md) [ Il\<compilatore >](compilers-element.md) elemento contiene zero o più [ \<elementi > del compilatore](compiler-element.md) . Ogni elemento > del compilatore specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico. [ \<](compiler-element.md)  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema dei file di configurazione](../index.md)
- [Schema di impostazioni del compilatore e del provider di linguaggi](index.md)
- [\<compiler> Element](compiler-element.md) (Elemento <compiler>)
