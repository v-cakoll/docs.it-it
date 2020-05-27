---
title: Globalizzazione e ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 6ea848d4a60069e6702b9d60fd90a55f572fb043
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842527"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="a6472-102">Globalizzazione .NET e ICU</span><span class="sxs-lookup"><span data-stu-id="a6472-102">.NET globalization and ICU</span></span>

<span data-ttu-id="a6472-103">In passato, le API di globalizzazione di .NET usavano librerie sottostanti diverse su piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="a6472-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="a6472-104">In UNIX, le API usavano i [componenti internazionali per Unicode (ICU)](http://site.icu-project.org/home)e in Windows hanno usato il [servizio NLS (National Language Support)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="a6472-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="a6472-105">Ciò ha comportato alcune differenze di comportamento in alcune API di globalizzazione durante l'esecuzione di applicazioni su piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="a6472-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="a6472-106">Le differenze di comportamento sono evidenti in queste aree:</span><span class="sxs-lookup"><span data-stu-id="a6472-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="a6472-107">Impostazioni cultura e dati delle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="a6472-107">Cultures and culture data</span></span>
- <span data-ttu-id="a6472-108">Maiuscole/minuscole stringa</span><span class="sxs-lookup"><span data-stu-id="a6472-108">String casing</span></span>
- <span data-ttu-id="a6472-109">Ordinamento e ricerca di stringhe</span><span class="sxs-lookup"><span data-stu-id="a6472-109">String sorting and searching</span></span>
- <span data-ttu-id="a6472-110">Chiavi di ordinamento</span><span class="sxs-lookup"><span data-stu-id="a6472-110">Sort keys</span></span>
- <span data-ttu-id="a6472-111">Normalizzazione delle stringhe</span><span class="sxs-lookup"><span data-stu-id="a6472-111">String normalization</span></span>
- <span data-ttu-id="a6472-112">Supporto dei nomi di dominio internazionalizzazione (IDN)</span><span class="sxs-lookup"><span data-stu-id="a6472-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="a6472-113">Nome visualizzato del fuso orario in Linux</span><span class="sxs-lookup"><span data-stu-id="a6472-113">Time zone display name on Linux</span></span>

<span data-ttu-id="a6472-114">A partire da .NET 5,0, gli sviluppatori hanno un maggiore controllo sulla libreria sottostante, consentendo alle applicazioni di evitare differenze tra le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="a6472-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="a6472-115">ICU per Windows</span><span class="sxs-lookup"><span data-stu-id="a6472-115">ICU on Windows</span></span>

<span data-ttu-id="a6472-116">Windows 10 May 2019 Update e versioni successive includono [ICU. dll](/windows/win32/intl/international-components-for-unicode--icu-) come parte del sistema operativo e .NET 5,0 e versioni successive usano ICU per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a6472-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="a6472-117">Quando è in esecuzione in Windows, .NET 5,0 e versioni successive tentano di caricare `icu.dll` e, se disponibile, lo usa per l'implementazione della globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a6472-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and if it's available, uses it for the globalization implementation.</span></span>  <span data-ttu-id="a6472-118">Se non è possibile trovare o caricare la libreria, ad esempio quando si eseguono versioni precedenti di Windows, .NET 5,0 e versioni successive eseguono il fallback all'implementazione basata su NLS.</span><span class="sxs-lookup"><span data-stu-id="a6472-118">If that library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="a6472-119">Anche quando si usa ICU, `CurrentCulture` i `CurrentUICulture` membri, e `CurrentRegion` usano ancora le API del sistema operativo Windows per rispettare le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="a6472-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="using-nls-instead-of-icu"></a><span data-ttu-id="a6472-120">Uso di NLS anziché di ICU</span><span class="sxs-lookup"><span data-stu-id="a6472-120">Using NLS instead of ICU</span></span>

<span data-ttu-id="a6472-121">L'uso di ICU anziché NLS può comportare differenze di comportamento con alcune operazioni correlate alla globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a6472-121">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="a6472-122">Per ripristinare l'utilizzo di NLS, uno sviluppatore può rifiutare esplicitamente l'implementazione di ICU.</span><span class="sxs-lookup"><span data-stu-id="a6472-122">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="a6472-123">Le applicazioni possono abilitare la modalità NLS in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6472-123">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="a6472-124">Nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="a6472-124">In the project file:</span></span>

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- <span data-ttu-id="a6472-125">Nel file `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="a6472-125">In the `runtimeconfig.json` file:</span></span>

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- <span data-ttu-id="a6472-126">Impostando la variabile di ambiente sul `DOTNET_SYSTEM_GLOBALIZATION_USENLS` valore `true` o `1` .</span><span class="sxs-lookup"><span data-stu-id="a6472-126">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="a6472-127">Un valore impostato nel progetto o nel file ha `runtimeconfig.json` la precedenza sulla variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="a6472-127">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="a6472-128">Per ulteriori informazioni, vedere [impostazioni di configurazione della fase di esecuzione](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="a6472-128">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="a6472-129">App-ICU locale</span><span class="sxs-lookup"><span data-stu-id="a6472-129">App-local ICU</span></span>

<span data-ttu-id="a6472-130">Ogni versione di ICU può comportare correzioni di bug it, oltre ai dati CLDR (Common locale data repository) che descrivono le lingue del mondo.</span><span class="sxs-lookup"><span data-stu-id="a6472-130">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="a6472-131">Il passaggio da una versione all'altra di ICU può influito leggermente sul comportamento dell'app quando si tratta di operazioni correlate alla globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a6472-131">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span>  <span data-ttu-id="a6472-132">Per consentire agli sviluppatori di applicazioni di garantire la coerenza tra tutte le distribuzioni, .NET 5,0 e versioni successive consentono alle app in Windows e UNIX di portare e usare la propria copia di ICU.</span><span class="sxs-lookup"><span data-stu-id="a6472-132">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="a6472-133">Le applicazioni possono acconsentire esplicitamente a una modalità di implementazione di un'applicazione ICU locale in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6472-133">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="a6472-134">Nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="a6472-134">In  the project file:</span></span>

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- <span data-ttu-id="a6472-135">Nel file `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="a6472-135">In the `runtimeconfig.json` file:</span></span>

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- <span data-ttu-id="a6472-136">Impostando la variabile di ambiente sul `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` valore `<suffix>:<version>` o `<version>` .</span><span class="sxs-lookup"><span data-stu-id="a6472-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

<span data-ttu-id="a6472-137">`<suffix>`: Suffisso facoltativo di lunghezza inferiore a 36 caratteri, che seguono le convenzioni di packaging di ICU pubblico.</span><span class="sxs-lookup"><span data-stu-id="a6472-137">`<suffix>`: Optional suffix of less than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="a6472-138">Quando si compila un ICU personalizzato, è possibile personalizzarlo per produrre i nomi di lib e i nomi dei simboli esportati in modo che contengano un suffisso, ad esempio, `libicuucmyapp` , dove `myapp` è il suffisso.</span><span class="sxs-lookup"><span data-stu-id="a6472-138">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

<span data-ttu-id="a6472-139">`<version>`: Versione di ICU valida, ad esempio 67,1.</span><span class="sxs-lookup"><span data-stu-id="a6472-139">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="a6472-140">Questa versione viene usata per caricare i file binari e ottenere i simboli esportati.</span><span class="sxs-lookup"><span data-stu-id="a6472-140">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="a6472-141">Per caricare ICU quando si imposta l'opzione app-local, .NET usa il <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> metodo, che esegue il probe di più percorsi.</span><span class="sxs-lookup"><span data-stu-id="a6472-141">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="a6472-142">Il metodo tenta innanzitutto di trovare la libreria nella `NATIVE_DLL_SEARCH_DIRECTORIES` proprietà, creata dall'host DotNet in base al `deps.json` file per l'app.</span><span class="sxs-lookup"><span data-stu-id="a6472-142">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="a6472-143">Per altre informazioni, vedere [Probe predefinito](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="a6472-143">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="a6472-144">Per le app indipendenti, non è richiesta alcuna azione speciale da parte dell'utente, ad eccezione del fatto che ICU si trova nella directory dell'app (per le app autosufficienti, il valore predefinito della directory di lavoro è `NATIVE_DLL_SEARCH_DIRECTORIES` ).</span><span class="sxs-lookup"><span data-stu-id="a6472-144">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="a6472-145">Se usi ICU tramite un pacchetto NuGet, funziona in applicazioni dipendenti dal Framework.</span><span class="sxs-lookup"><span data-stu-id="a6472-145">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="a6472-146">NuGet risolve gli asset nativi e li include nel `deps.json` file e nella directory di output per l'applicazione nella `runtimes` Directory.</span><span class="sxs-lookup"><span data-stu-id="a6472-146">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="a6472-147">.NET lo carica da questa posizione.</span><span class="sxs-lookup"><span data-stu-id="a6472-147">.NET loads it from there.</span></span>

<span data-ttu-id="a6472-148">Per le app dipendenti dal Framework (non indipendenti) in cui ICU viene utilizzato da una compilazione locale, è necessario eseguire passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a6472-148">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="a6472-149">.NET SDK non dispone ancora di una funzionalità per i file binari nativi "Loose" da incorporare in `deps.json` (vedere [questo problema SDK](https://github.com/dotnet/sdk/issues/11373)).</span><span class="sxs-lookup"><span data-stu-id="a6472-149">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="a6472-150">In alternativa, è possibile abilitare questa operazione aggiungendo informazioni aggiuntive nel file di progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a6472-150">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="a6472-151">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6472-151">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="a6472-152">Questa operazione deve essere eseguita per tutti i file binari di ICU per i runtime supportati.</span><span class="sxs-lookup"><span data-stu-id="a6472-152">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="a6472-153">Inoltre, i `NuGetPackageId` metadati nel `RuntimeTargetsCopyLocalItems` gruppo di elementi devono corrispondere a un pacchetto NuGet a cui fa effettivamente riferimento il progetto.</span><span class="sxs-lookup"><span data-stu-id="a6472-153">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="a6472-154">comportamento macOS</span><span class="sxs-lookup"><span data-stu-id="a6472-154">macOS behavior</span></span>

<span data-ttu-id="a6472-155">`macOS`ha un comportamento diverso per la risoluzione delle librerie dinamiche dipendenti dai comandi di caricamento specificati nel `match-o` file rispetto al caricatore Linux.</span><span class="sxs-lookup"><span data-stu-id="a6472-155">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="a6472-156">Nel caricatore Linux, .NET può provare `libicudata` , `libicuuc` e `libicui18n` (in questo ordine) per soddisfare il grafico delle dipendenze di ICU.</span><span class="sxs-lookup"><span data-stu-id="a6472-156">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="a6472-157">Tuttavia, in macOS questa operazione non funziona.</span><span class="sxs-lookup"><span data-stu-id="a6472-157">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="a6472-158">Quando si compila ICU in macOS, per impostazione predefinita si ottiene una libreria dinamica con questi comandi di caricamento in `libicuuc` .</span><span class="sxs-lookup"><span data-stu-id="a6472-158">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="a6472-159">Per esempio.:</span><span class="sxs-lookup"><span data-stu-id="a6472-159">For example.:</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="a6472-160">Questi comandi fanno riferimento solo al nome delle librerie dipendenti per gli altri componenti di ICU.</span><span class="sxs-lookup"><span data-stu-id="a6472-160">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="a6472-161">Il caricatore esegue la ricerca seguendo le `dlopen` convenzioni, che comporta la presenza di queste librerie nelle directory di sistema o l'impostazione di `LD_LIBRARY_PATH` env var oppure la presenza di ICU nella directory a livello di app.</span><span class="sxs-lookup"><span data-stu-id="a6472-161">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="a6472-162">Se non è possibile impostare `LD_LIBRARY_PATH` o assicurarsi che i file binari di ICU si trovino nella directory a livello di app, è necessario eseguire alcune operazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a6472-162">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="a6472-163">Sono disponibili alcune direttive per il caricatore, ad esempio `@loader_path` , che indicano al caricatore di cercare tale dipendenza nella stessa directory del file binario con il comando Load.</span><span class="sxs-lookup"><span data-stu-id="a6472-163">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="a6472-164">A questo scopo è possibile procedere in due modi:</span><span class="sxs-lookup"><span data-stu-id="a6472-164">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="a6472-165">Eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6472-165">Run the following commands:</span></span>

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- <span data-ttu-id="a6472-166">Patch ICU per produrre i nomi di installazione con`@loader_path`</span><span class="sxs-lookup"><span data-stu-id="a6472-166">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="a6472-167">Prima di eseguire autoconf ( `./runConfigureICU` ), modificare [le righe seguenti](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) in:</span><span class="sxs-lookup"><span data-stu-id="a6472-167">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```
