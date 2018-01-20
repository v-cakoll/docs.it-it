---
title: '&lt;providerOption&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: "22"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f28b7b43f2f782744a0dbc81bd0b91bbbcd8abba
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltprovideroptiongt-element"></a>&lt;providerOption&gt; elemento
Specifica gli attributi di versione del compilatore per un provider del linguaggio.  
  
 \<Elemento di configurazione >  
\<system.codedom Element>  
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
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome dell'opzione. ad esempio, "CompilerVersion".|  
|`value`|Attributo obbligatorio.<br /><br /> Specifica il valore per l'opzione. ad esempio, "v 3.5".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|  
|[\<i compilatori > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenitore per elementi di configurazione del compilatore. contiene zero o più `<compiler>` elementi.|  
|[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)|Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3.5, il provider di codice Code Document Object Model (CodeDOM) può supportare opzioni specifiche del provider utilizzando il `<providerOption>` elemento.  
  
 .NET Framework 3.5 include gli assembly di .NET Framework 2.0 aggiornati e fornisce nuovi assembly versione 3.5 contenenti nuovi tipi. I provider di codice Microsoft c# e Visual Basic sono contenuti in assembly .NET Framework 2.0, ma sono stati aggiornati per supportare i compilatori versione 3.5. Per impostazione predefinita, i provider di codice aggiornato generano codice per i compilatori versione 2.0. È possibile utilizzare il `<providerOption>` elemento per modificare la versione del compilatore di destinazione in 3.5. A tale scopo, specificare "CompilerVersion" per il `name` attributo e "v 3.5" per il `value` attributo. È necessario anteporre il numero di versione con una lettera minuscola "v".  
  
 È possibile rendere la specifica della versione globale aggiungendo il `<providerOption>` elemento per il file Machine. config di .NET Framework 2.0 o un file Web. config radice. Se si aggiorna la versione del compilatore predefinita in 3.5 nel file Machine. config, è possibile ripristinare 2.0 per ogni applicazione utilizzando il `<providerOption>` elemento nel file di configurazione dell'applicazione.  
  
 Gli implementatori di provider di codice codeDOM possono elaborare opzioni personalizzate fornendo un costruttore che accetta un `providerOptions` parametro di tipo <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare la versione 3.5 del provider di codice c# deve essere utilizzata.  
  
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
 [compilatore elemento per i compilatori per compilation (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
