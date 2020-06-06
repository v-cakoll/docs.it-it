---
title: Schema di impostazioni del compilatore e del provider di linguaggi
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 5b1f9684ad26d4a03769af287fc8b0c0c7c4cc1a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088689"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="d9aff-102">Schema di impostazioni del compilatore e del provider di linguaggi</span><span class="sxs-lookup"><span data-stu-id="d9aff-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="d9aff-103">Le impostazioni del compilatore e del provider di linguaggi specificano gli elementi di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="d9aff-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="d9aff-104">Ogni elemento di configurazione del compilatore specifica il nome del tipo di provider di codice, i parametri del compilatore, i nomi dei linguaggi supportati e le estensioni di file supportate.</span><span class="sxs-lookup"><span data-stu-id="d9aff-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="d9aff-105">.NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d9aff-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="d9aff-106">Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="d9aff-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="d9aff-107">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.</span><span class="sxs-lookup"><span data-stu-id="d9aff-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)
  
|<span data-ttu-id="d9aff-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9aff-108">Element</span></span>|<span data-ttu-id="d9aff-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9aff-109">Description</span></span>|  
|-------------|-----------------|  
|[\<system.codedom>](system-codedom-element.md)|<span data-ttu-id="d9aff-110">Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="d9aff-110">Specifies compiler configuration settings for available language providers.</span></span>|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="d9aff-111">Contenitore per gli elementi di configurazione del compilatore; contiene zero o più [\<compiler>](compiler-element.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="d9aff-111">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[\<compiler>](compiler-element.md)|<span data-ttu-id="d9aff-112">Specifica gli attributi di configurazione del compilatore per un provider del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="d9aff-112">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9aff-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9aff-113">Example</span></span>  
 <span data-ttu-id="d9aff-114">L'esempio seguente illustra un elemento di configurazione del compilatore tipico.</span><span class="sxs-lookup"><span data-stu-id="d9aff-114">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9aff-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d9aff-115">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="d9aff-116">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d9aff-116">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d9aff-117">\<compiler>Elemento</span><span class="sxs-lookup"><span data-stu-id="d9aff-117">\<compiler> Element</span></span>](compiler-element.md)
