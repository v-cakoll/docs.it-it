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
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088049"
---
# <a name="compiler-element"></a>\<compiler> Elemento

Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

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
|`compilerOptions`|Attributo facoltativo.<br /><br /> Specifica argomenti aggiuntivi specifici del compilatore per la compilazione. I valori per l' `compilerOptions` attributo sono in genere elencati in un argomento delle opzioni del compilatore per il compilatore.|
|`extension`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punti e virgola delle estensioni di file utilizzate dai file di origine per il provider del linguaggio. come ad esempio ".cs".|
|`language`|Attributo obbligatorio.<br /><br /> Fornisce un elenco delimitato da punti e virgola di nomi di lingua supportati dal provider del linguaggio. come ad esempio "C#;cs;csharp".|
|`type`|Attributo obbligatorio.<br /><br /> Specifica il nome del tipo del provider del linguaggio, incluso il nome dell'assembly che contiene l'implementazione del provider. Il nome del tipo deve soddisfare i requisiti definiti nella [specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Attributo facoltativo.<br /><br /> Specifica il livello di avviso predefinito del compilatore. determina il livello al quale il provider del linguaggio considera gli avvisi di compilazione come errori.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<providerOption>Elemento](provideroption-element.md)|Specifica gli attributi della versione del compilatore per un provider di linguaggio.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<configuration>Elemento](../configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|[\<system.codedom>Elemento](system-codedom-element.md)|Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.|
|[\<compilers>Elemento](compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore; contiene zero o più `<compiler>` elementi.|

## <a name="remarks"></a>Commenti

Ogni `<compiler>` elemento specifica gli attributi di configurazione del compilatore per un provider di linguaggio specifico. Il provider estende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> classe per un linguaggio specifico. l' `<compiler>` elemento definisce le impostazioni del compilatore e del generatore di codice per il provider del linguaggio.

.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.

Gli elementi del compilatore nel file di configurazione dell'applicazione o del Web possono completare o sostituire le impostazioni nel file di configurazione del computer. Se è configurata più di un'implementazione del provider per lo stesso nome di linguaggio o per la stessa estensione di file, l'ultima configurazione corrispondente sostituisce tutti i provider configurati in precedenza per il nome o l'estensione di file.

## <a name="configuration-file"></a>File di configurazione

Questo elemento può essere utilizzato nel file di configurazione del computer e nel file di configurazione dell'applicazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato un tipico elemento di configurazione del compilatore:

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

## <a name="see-also"></a>Vedi anche

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema del file di configurazione](../index.md)
- [\<compilers>Elemento](compilers-element.md)
- [Specifica di nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento compiler per compilers per compilation (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
