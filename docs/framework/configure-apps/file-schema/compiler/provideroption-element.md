---
title: <providerOption> Elemento
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088666"
---
# <a name="provideroption-element"></a>\<elemento > providerOption
Specifica gli attributi della versione del compilatore per un provider di linguaggio.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. codedom >** ](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**compilatori**](compilers-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> [**del compilatore**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption** >

## <a name="syntax"></a>Sintassi  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome dell'opzione. ad esempio, "CompilerVersion".|  
|`value`|Attributo obbligatorio.<br /><br /> Specifica il valore per l'opzione. ad esempio, "v 3.5".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<configuration>](../configuration-element.md)|Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.|  
|[Elemento \<System. CodeDom >](system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<> elemento compilatori](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero o più elementi `<compiler>`.|  
|[\<compiler> Element](compiler-element.md) (Elemento <compiler>)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3,5 i provider di codice Code Document Object Model (CodeDOM) possono supportare opzioni specifiche del provider tramite l'elemento `<providerOption>`.  
  
 Il .NET Framework 3,5 include gli assembly .NET Framework 2,0 aggiornati e fornisce nuovi assembly della versione 3,5 che contengono nuovi tipi. I provider C# di codice Microsoft e Visual Basic sono contenuti in .NET Framework assembly 2,0, ma sono stati aggiornati per supportare i compilatori della versione 3,5. Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori della versione 2,0. È possibile usare l'elemento `<providerOption>` per modificare la versione del compilatore di destinazione in 3,5. A tale scopo, specificare "CompilerVersion" per l'attributo `name` e "v 3.5" per l'attributo `value`. Il numero di versione deve essere preceduto da un minuscolo "v".  
  
 Per rendere la specifica della versione globale, è possibile aggiungere l'elemento `<providerOption>` al .NET Framework 2,0 Machine. config o al file Web. config radice. Se si aggiorna la versione del compilatore predefinita a 3,5 nel file Machine. config, è possibile reimpostarla su 2,0 per ogni singola applicazione usando l'elemento `<providerOption>` nel file di configurazione dell'applicazione.  
  
 Gli implementatori del provider di codice CodeDOM possono elaborare opzioni personalizzate fornendo un costruttore che accetta un parametro `providerOptions` di tipo <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la C# versione 3,5 del provider di codice.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema dei file di configurazione](../index.md)
- [\<> elemento compilatori](compilers-element.md)
- [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)
- [Elemento Compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
