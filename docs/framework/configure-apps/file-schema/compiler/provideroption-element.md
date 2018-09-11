---
title: '&lt;providerOption&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 75cc2003a88cc7be467b9062c37b6b5d9eb82f53
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365030"
---
# <a name="ltprovideroptiongt-element"></a>&lt;providerOption&gt; elemento
Specifica gli attributi di versione del compilatore per un provider del linguaggio.  
  
 \<Elemento Configuration >  
\<Elemento System. CodeDom >  
\<Elemento compilers >  
\<compilatore > elemento  
\<providerOption > elemento  
  
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
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome dell'opzione; ad esempio, "CompilerVersion".|  
|`value`|Attributo obbligatorio.<br /><br /> Specifica il valore per l'opzione. ad esempio, "v3.5".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<System. CodeDom > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<i compilatori > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.|  
|[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3.5, i provider di codice Code Document Object Model (CodeDOM) possono supportare opzioni specifiche del provider usando la `<providerOption>` elemento.  
  
 .NET Framework 3.5 include gli assembly di .NET Framework 2.0 aggiornati e fornisce nuovi assembly della versione 3.5 che contengono nuovi tipi. I provider di codice Microsoft c# e Visual Basic sono contenuti negli assembly di .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori di versione 3.5. Per impostazione predefinita, i provider di codice aggiornato generano codice per i compilatori di versione 2.0. È possibile usare il `<providerOption>` elemento per modificare la versione del compilatore di destinazione a 3.5. A questo scopo, specificare "CompilerVersion" per il `name` attributo e "v3.5" per il `value` attributo. È necessario anteporre il numero di versione con lettere minuscole "v".  
  
 È possibile rendere la specifica della versione globale mediante l'aggiunta di `<providerOption>` elemento per il file Machine. config di .NET Framework 2.0 o un file Web. config radice. Se si aggiorna la versione del compilatore predefinito 3.5 nel file Machine. config, è possibile modificarlo al 2.0 su una base all'applicazione tramite il `<providerOption>` elemento nel file di configurazione dell'applicazione.  
  
 I responsabili dell'implementazione del provider di codice codeDOM può elaborare le opzioni personalizzate, fornendo un costruttore che accetta un `providerOptions` parametru typu <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare la versione 3.5 del provider di codice c# da usare.  
  
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
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<i compilatori > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)  
 [Elemento Compiler per compilers per compilation (Schema delle impostazioni ASP.NET)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
