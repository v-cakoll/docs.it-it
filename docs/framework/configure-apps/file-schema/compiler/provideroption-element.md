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
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155401"
---
# <a name="provideroption-element"></a>\<providerOption> Elemento
Specifica gli attributi della versione del compilatore per un provider di linguaggio.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

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
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>Elemento](../configuration-element.md)|Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<system.codedom>Elemento](system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<compilers>Elemento](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.|  
|[\<compiler>Elemento](compiler-element.md)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="remarks"></a>Commenti  
 In .NET Framework versione 3,5 i provider di codice Code Document Object Model (CodeDOM) possono supportare opzioni specifiche del provider tramite l' `<providerOption>` elemento.  
  
 Il .NET Framework 3,5 include gli assembly .NET Framework 2,0 aggiornati e fornisce nuovi assembly della versione 3,5 che contengono nuovi tipi. I provider di codice Microsoft C# e Visual Basic sono contenuti in .NET Framework assembly 2,0, ma sono stati aggiornati per supportare i compilatori della versione 3,5. Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori della versione 2,0. È possibile usare l' `<providerOption>` elemento per modificare la versione del compilatore di destinazione in 3,5. A tale scopo, specificare "CompilerVersion" per l' `name` attributo e "v 3.5" per l' `value` attributo. Il numero di versione deve essere preceduto da un minuscolo "v".  
  
 È possibile rendere globale la specifica della versione aggiungendo l' `<providerOption>` elemento al file di .NET Framework 2,0 Machine. config o al file Web. config radice. Se si aggiorna la versione del compilatore predefinita a 3,5 nel file Machine. config, è possibile reimpostarla su 2,0 per ogni singola applicazione usando l' `<providerOption>` elemento nel file di configurazione dell'applicazione.  
  
 Gli implementatori del provider di codice CodeDOM possono elaborare opzioni personalizzate fornendo un costruttore che accetta un `providerOptions` parametro di tipo <xref:System.Collections.Generic.IDictionary%602> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la versione 3,5 del provider di codice C#.  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema del file di configurazione](../index.md)
- [\<compilers>Elemento](compilers-element.md)
- [Specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
