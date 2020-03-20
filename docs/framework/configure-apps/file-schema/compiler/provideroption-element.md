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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155401"
---
# <a name="provideroption-element"></a>\<Elemento> providerOption
Specifica gli attributi di versione del compilatore per un provider del linguaggio.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.codedom**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilatori>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del compilatore**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>providerOption**

## <a name="syntax"></a>Sintassi  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome dell'opzione. ad esempio, "CompilerVersion".|  
|`value`|Attributo obbligatorio.<br /><br /> Specifica il valore per l'opzione. ad esempio, "v3.5".|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Elemento> configurazione](../configuration-element.md)|Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<system.codedom>elemento](system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<compilers> Element](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero `<compiler>` o più elementi.|  
|[\<> del compilatore](compiler-element.md)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="remarks"></a>Osservazioni  
 In .NET Framework versione 3.5 i provider di codice CodeDOM (Code Document `<providerOption>` Object Model) possono supportare opzioni specifiche del provider tramite l'elemento .  
  
 .NET Framework 3.5 include assembly .NET Framework 2.0 aggiornati e fornisce assembly della nuova versione 3.5 che contengono nuovi tipi. I provider di codice di Microsoft C e Visual Basic sono contenuti negli assembly di .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori versione 3.5. Per impostazione predefinita, i provider di codice aggiornati generano codice per i compilatori versione 2.0.By default, the updated code providers generate code for version 2.0 compilers. È possibile `<providerOption>` utilizzare l'elemento per modificare la versione del compilatore di destinazione a 3.5.You can use the element to change the target compiler version to 3.5. A tale scopo, specificare "CompilerVersion" per `name` l'attributo `value` e "v3.5" per l'attributo. È necessario far precedere il numero di versione da una "v" minuscola.  
  
 È possibile rendere globale la `<providerOption>` specifica della versione aggiungendo l'elemento al file Machine.config o Web.config radice di .NET Framework 2.0. Se si aggiorna la versione predefinita del compilatore a 3.5 nel file Machine.config, è possibile `<providerOption>` ripristinarla a 2.0 in base all'applicazione utilizzando l'elemento nel file di configurazione dell'applicazione.  
  
 Gli implementatori del provider di codice CodeDOM possono `providerOptions` elaborare <xref:System.Collections.Generic.IDictionary%602>opzioni personalizzate fornendo un costruttore che accetta un parametro di tipo .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che deve essere utilizzata la versione 3.5 del provider di codice C .  
  
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
- [Schema del file di configurazione](../index.md)
- [\<compilers> Element](compilers-element.md)
- [Specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
