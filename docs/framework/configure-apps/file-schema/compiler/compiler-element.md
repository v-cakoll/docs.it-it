---
title: <compiler> Elemento
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 34753d538ff37ac4ae621f653d47ac92ac6749a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705376"
---
# <a name="compiler-element"></a>\<compilatore > elemento

Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.

\<Elemento Configuration > \<elemento System. CodeDom > \<compilatori elemento > \<compilatore > elemento

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
|`compilerOptions`|Attributo facoltativo.<br /><br /> Specifica ulteriori argomenti specifici del compilatore per la compilazione. I valori per il `compilerOptions` attributo vengono elencati in genere in un argomento relativo alle opzioni del compilatore per consentire al compilatore.|
|`extension`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punto e virgola di estensioni di file usato dai file di origine per il provider del linguaggio. Ad esempio, "cs".|
|`language`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punto e virgola di nomi di linguaggio supportati dal provider del linguaggio. Ad esempio "c#; cs; csharp".|
|`type`|Attributo obbligatorio.<br /><br /> Specifica il nome del tipo di provider del linguaggio, inclusi il nome dell'assembly contenente l'implementazione del provider. Il nome del tipo deve soddisfare i requisiti definiti nella [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Attributo facoltativo.<br /><br /> Specifica il livello di avviso del compilatore predefinito; Determina il livello in corrispondenza del quale il provider del linguaggio avvisi di compilazione vengono considerati come errori.|

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

Gli elementi del compilatore nel file di configurazione Web o applicazione possono integrare o sostituire le impostazioni nel file di configurazione del computer. Se più di un'implementazione di provider è configurata per lo stesso nome di linguaggio o la stessa estensione di file, l'ultima configurazione corrisponda esegue l'override di qualsiasi provider precedentemente configurato per tale estensione di file o nome di linguaggio.

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.

## <a name="example"></a>Esempio

L'esempio seguente illustra un elemento di configurazione del compilatore tipico:

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

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<i compilatori > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md) (Specifica di nomi di tipo completi)
- [Elemento Compiler per compilers per compilation (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
