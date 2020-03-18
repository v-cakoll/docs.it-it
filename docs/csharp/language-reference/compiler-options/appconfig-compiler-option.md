---
title: -appconfig (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 7a7e8e61f65704a2e99385a1be320048d950324c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69922514"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="7a23b-102">-appconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="7a23b-102">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="7a23b-103">L'opzione **-appconfig** del compilatore consente a un'applicazione C# di specificare il percorso del file di configurazione (app.config) dell'applicazione di un assembly per Common Language Runtime (CLR) in fase di associazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a23b-103">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a23b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a23b-104">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a23b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7a23b-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="7a23b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7a23b-106">Required.</span></span> <span data-ttu-id="7a23b-107">Il file di configurazione dell'applicazione che contiene le impostazioni di associazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a23b-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a23b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7a23b-108">Remarks</span></span>  
 <span data-ttu-id="7a23b-109">L'opzione **-appconfig** può essere usata anche in scenari avanzati nei quali un assembly deve fare riferimento allo stesso tempo alla versione di .NET Framework e a quella di .NET Framework per Silverlight di un particolare assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7a23b-109">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="7a23b-110">Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe fare riferimento al desktop WPF, per l'interfaccia utente della finestra di progettazione, e al subset di WPF incluso in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="7a23b-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="7a23b-111">Lo stesso assembly della finestra di progettazione deve accedere a entrambi gli assembly.</span><span class="sxs-lookup"><span data-stu-id="7a23b-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="7a23b-112">Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly.</span><span class="sxs-lookup"><span data-stu-id="7a23b-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="7a23b-113">L'opzione **-appconfig** del compilatore consente di specificare il percorso del file app.config che disabilita il comportamento predefinito tramite un tag `<supportPortability>`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7a23b-113">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="7a23b-114">Il compilatore passa il percorso del file alla logica di associazione degli assembly di CLR.</span><span class="sxs-lookup"><span data-stu-id="7a23b-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a23b-115">Se si usa Microsoft Build Engine (MSBuild) per compilare l'applicazione, è possibile impostare l'opzione **-appconfig** del compilatore aggiungendo un tag di proprietà al file con estensione csproj.</span><span class="sxs-lookup"><span data-stu-id="7a23b-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="7a23b-116">Per usare il file app.config già impostato nel progetto, aggiungere un tag di proprietà `<UseAppConfigForCompiler>` al file con estensione csproj e impostarne il valore su `true`.</span><span class="sxs-lookup"><span data-stu-id="7a23b-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="7a23b-117">Per specificare un file app.config diverso, aggiungere un tag di proprietà `<AppConfigForCompiler>` e impostarne il valore sul percorso del file.</span><span class="sxs-lookup"><span data-stu-id="7a23b-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a23b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a23b-118">Example</span></span>  
 <span data-ttu-id="7a23b-119">L'esempio seguente illustra un file app.config che consente a un'applicazione di fare riferimento all'implementazione di .NET Framework e di .NET Framework per Silverlight per qualsiasi assembly di .NET Framework presente in entrambe le implementazioni.</span><span class="sxs-lookup"><span data-stu-id="7a23b-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="7a23b-120">L'opzione **-appconfig** del compilatore specifica il percorso di questo file app.config.</span><span class="sxs-lookup"><span data-stu-id="7a23b-120">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a23b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a23b-121">See also</span></span>

- [<span data-ttu-id="7a23b-122">\<Elemento> supportPortability</span><span class="sxs-lookup"><span data-stu-id="7a23b-122">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [<span data-ttu-id="7a23b-123">Opzioni del compilatore C# in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="7a23b-123">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
