---
title: '&lt;compilatore&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2ef50301a5188193cc13cd0e657f53593ef0d93e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcompilergt-element"></a>&lt;compilatore&gt; elemento
Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.  
  
 \<Elemento di configurazione >  
\<Elemento System. CodeDom >  
\<Elemento compilers >  
\<compilatore > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`compilerOptions`|Attributo facoltativo.<br /><br /> Specifica ulteriori argomenti specifici del compilatore per la compilazione. I valori per il `compilerOptions` attributo sono in genere elencati in un argomento di opzioni del compilatore per il compilatore. Nella documentazione di Visual Studio 2005, è possibile individuare le opzioni del compilatore cercando "opzioni del compilatore" nell'indice.|  
|`extension`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punto e virgola di estensioni di file utilizzato dai file di origine per il provider del linguaggio. Ad esempio, "cs".|  
|`language`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punto e virgola di nomi della lingua supportate dal provider del linguaggio. Ad esempio, "c#; cs; csharp".|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il nome del tipo di provider del linguaggio, inclusi il nome dell'assembly contenente l'implementazione del provider. Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`warningLevel`|Attributo facoltativo.<br /><br /> Specifica il livello di avviso del compilatore predefinito; Determina il livello in corrispondenza del quale il provider del linguaggio considera gli avvisi di compilazione come errori.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<providerOption > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Specifica gli attributi di versione del compilatore per un provider del linguaggio.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|[\<System. CodeDom > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<i compilatori > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.|  
  
## <a name="remarks"></a>Note  
 Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico. Estende il provider di <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico; il `<compiler>` elemento definisce il compilatore e le impostazioni del generatore di codice per il provider del linguaggio.  
  
 .NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.  
  
 Elementi del compilatore all'applicazione o un file di configurazione Web possono integrare o sostituire le impostazioni nel file di configurazione del computer. Se più di un'implementazione del provider è configurata per lo stesso nome di lingua o la stessa estensione, l'ultima configurazione corrispondente esegue l'override di qualsiasi provider precedentemente configurato per tale estensione di file o nome di linguaggio.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione del computer e i file di configurazione dell'applicazione.  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
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
 [compilatore elemento per i compilatori per compilation (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
