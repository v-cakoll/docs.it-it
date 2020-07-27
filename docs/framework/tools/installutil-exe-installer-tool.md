---
title: Installutil.exe (Strumento Programma di installazione)
description: Utilizzare Installutil.exe utilità di installazione. Questo strumento consente di installare o disinstallare le risorse del server eseguendo i componenti del programma di installazione negli assembly specificati.
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: 042e5f64a7a863173db9c4e601d3152b0df46d97
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164447"
---
# <a name="installutilexe-installer-tool"></a><span data-ttu-id="b02c4-104">Installutil.exe (Strumento Programma di installazione)</span><span class="sxs-lookup"><span data-stu-id="b02c4-104">Installutil.exe (Installer Tool)</span></span>

<span data-ttu-id="b02c4-105">Lo strumento Programma di installazione è un'utilità da riga di comando che consente di installare e disinstallare le risorse del server eseguendo i componenti del programma di installazione di assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="b02c4-105">The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing the installer components in specified assemblies.</span></span> <span data-ttu-id="b02c4-106">Questo strumento funziona insieme alle classi nello spazio dei nomi <xref:System.Configuration.Install>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-106">This tool works in conjunction with classes in the <xref:System.Configuration.Install> namespace.</span></span>

<span data-ttu-id="b02c4-107">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b02c4-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b02c4-108">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="b02c4-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b02c4-109">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b02c4-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="b02c4-110">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b02c4-110">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="b02c4-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b02c4-111">Syntax</span></span>

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a><span data-ttu-id="b02c4-112">Parametri</span><span class="sxs-lookup"><span data-stu-id="b02c4-112">Parameters</span></span>

|<span data-ttu-id="b02c4-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="b02c4-113">Argument</span></span>|<span data-ttu-id="b02c4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b02c4-114">Description</span></span>|
|--------------|-----------------|
|`assembly`|<span data-ttu-id="b02c4-115">Nome file dell'assembly in cui eseguire i componenti del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-115">The file name of the assembly in which to execute the installer components.</span></span> <span data-ttu-id="b02c4-116">Omettere questo parametro se si desidera specificare il nome sicuro dell'assembly utilizzando l'opzione `/AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-116">Omit this parameter if you want to specify the assembly's strong name by using the `/AssemblyName` option.</span></span>|

<a name="options"></a>

## <a name="options"></a><span data-ttu-id="b02c4-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b02c4-117">Options</span></span>

|<span data-ttu-id="b02c4-118">Opzione</span><span class="sxs-lookup"><span data-stu-id="b02c4-118">Option</span></span>|<span data-ttu-id="b02c4-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b02c4-119">Description</span></span>|
|------------|-----------------|
|`/h[elp]`<br /><br /> <span data-ttu-id="b02c4-120">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b02c4-120">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="b02c4-121">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b02c4-121">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="b02c4-122">`/help`*assembly* di</span><span class="sxs-lookup"><span data-stu-id="b02c4-122">`/help` *assembly*</span></span><br /><br /> <span data-ttu-id="b02c4-123">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b02c4-123">-or-</span></span><br /><br /> <span data-ttu-id="b02c4-124">`/?`*assembly* di</span><span class="sxs-lookup"><span data-stu-id="b02c4-124">`/?` *assembly*</span></span>|<span data-ttu-id="b02c4-125">Visualizza le opzioni aggiuntive riconosciute dai singoli programmi di installazione all'interno dell'assembly specificato, insieme alla sintassi e alle opzioni di comando di InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="b02c4-125">Displays additional options recognized by individual installers within the specified assembly, along with command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="b02c4-126">Questa opzione aggiunge il testo restituito dalla proprietà <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> di ogni componente del programma di installazione al testo della Guida di InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="b02c4-126">This option adds the text returned by each installer component's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property to the help text of InstallUtil.exe.</span></span>|
|<span data-ttu-id="b02c4-127">`/AssemblyName`"*AssemblyName*</span><span class="sxs-lookup"><span data-stu-id="b02c4-127">`/AssemblyName` "*assemblyName*</span></span><br /><br /> <span data-ttu-id="b02c4-128">,Version=*major.minor.build.revision*</span><span class="sxs-lookup"><span data-stu-id="b02c4-128">,Version=*major.minor.build.revision*</span></span><br /><br /> <span data-ttu-id="b02c4-129">,Culture=*locale*</span><span class="sxs-lookup"><span data-stu-id="b02c4-129">,Culture=*locale*</span></span><br /><br /> <span data-ttu-id="b02c4-130">,PublicKeyToken=*publicKeyToken*"</span><span class="sxs-lookup"><span data-stu-id="b02c4-130">,PublicKeyToken=*publicKeyToken*"</span></span>|<span data-ttu-id="b02c4-131">Specifica il nome sicuro di un assembly, che verrà registrato nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="b02c4-131">Specifies the strong name of an assembly, which must be registered in the global assembly cache.</span></span> <span data-ttu-id="b02c4-132">Il nome dell'assembly deve essere completo, con versione, impostazioni cultura e token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="b02c4-132">The assembly name must be fully qualified with the version, culture, and public key token of the assembly.</span></span> <span data-ttu-id="b02c4-133">Il nome completo deve essere racchiuso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="b02c4-133">The fully qualified name must be surrounded by quotes.</span></span><br /><br /> <span data-ttu-id="b02c4-134">Ad esempio, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" è un nome di assembly completo.</span><span class="sxs-lookup"><span data-stu-id="b02c4-134">For example, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" is a fully qualified assembly name.</span></span>|
|<span data-ttu-id="b02c4-135">`/InstallStateDir=[`*DirectoryName*`]`</span><span class="sxs-lookup"><span data-stu-id="b02c4-135">`/InstallStateDir=[` *directoryName* `]`</span></span>|<span data-ttu-id="b02c4-136">Specifica la directory del file con estensione InstallState contenente i dati utilizzati per la disinstallazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b02c4-136">Specifies the directory of the .InstallState file that contains the data used to uninstall the assembly.</span></span> <span data-ttu-id="b02c4-137">La directory predefinita è quella che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b02c4-137">The default is the directory that contains the assembly.</span></span>|
|<span data-ttu-id="b02c4-138">`/LogFile=`[*nome file*]</span><span class="sxs-lookup"><span data-stu-id="b02c4-138">`/LogFile=`[*filename*]</span></span>|<span data-ttu-id="b02c4-139">Specifica il nome del file di log in cui è registrato lo stato dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-139">Specifies the name of the log file where installation progress is recorded.</span></span> <span data-ttu-id="b02c4-140">Per impostazione predefinita, se l'opzione `/LogFile` viene omessa, viene creato un file di log denominato *assemblyname*.InstallLog.</span><span class="sxs-lookup"><span data-stu-id="b02c4-140">By default, if the `/LogFile` option is omitted, a log file named *assemblyname*.InstallLog is created.</span></span> <span data-ttu-id="b02c4-141">Se *filename* viene omesso, non verrà generato alcun file di log.</span><span class="sxs-lookup"><span data-stu-id="b02c4-141">If *filename* is omitted, no log file is generated.</span></span>|
|<span data-ttu-id="b02c4-142">`/LogToConsole`={`true`&#124;`false`}</span><span class="sxs-lookup"><span data-stu-id="b02c4-142">`/LogToConsole`={`true`&#124;`false`}</span></span>|<span data-ttu-id="b02c4-143">Se `true`, visualizza l'output sulla console.</span><span class="sxs-lookup"><span data-stu-id="b02c4-143">If `true`, displays output to the console.</span></span> <span data-ttu-id="b02c4-144">Se `false` (impostazione predefinita), evita la visualizzazione dell'output sulla console.</span><span class="sxs-lookup"><span data-stu-id="b02c4-144">If `false` (the default), suppresses output to the console.</span></span>|
|`/ShowCallStack`|<span data-ttu-id="b02c4-145">Restituisce lo stack di chiamate al file di log se si verifica un'eccezione durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-145">Outputs the call stack to the log file if an exception occurs at any point during installation.</span></span>|
|<span data-ttu-id="b02c4-146">`/u`[`ninstall`]</span><span class="sxs-lookup"><span data-stu-id="b02c4-146">`/u`[`ninstall`]</span></span>|<span data-ttu-id="b02c4-147">Disinstalla gli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="b02c4-147">Uninstalls the specified assemblies.</span></span> <span data-ttu-id="b02c4-148">A differenza delle altre opzioni, `/u` si applica a tutti gli assembly, indipendentemente dalla posizione dell'opzione nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b02c4-148">Unlike the other options, `/u` applies to all assemblies regardless of where the option appears on the command line.</span></span>|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a><span data-ttu-id="b02c4-149">Opzioni aggiuntive del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="b02c4-149">Additional Installer Options</span></span>

<span data-ttu-id="b02c4-150">I singoli programmi di installazione usati all'interno di un assembly sono in grado di riconoscere opzioni oltre a quelle elencate nella sezione [Opzioni](#options).</span><span class="sxs-lookup"><span data-stu-id="b02c4-150">Individual installers used within an assembly may recognize options in addition to those listed in the [Options](#options) section.</span></span> <span data-ttu-id="b02c4-151">Per ulteriori informazioni su queste opzioni, eseguire InstallUtil.exe con i percorsi degli assembly sulla riga di comando con l'opzione `/?` o `/help`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-151">To learn about these options, run InstallUtil.exe with the paths of the assemblies on the command line along with the `/?` or `/help` option.</span></span> <span data-ttu-id="b02c4-152">Per specificare queste opzioni, includerle nella riga di comando con le opzioni riconosciute da InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="b02c4-152">To specify these options, you include them on the command line along with the options recognized by InstallUtil.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="b02c4-153">Il testo della Guida sulle opzioni supportate da singoli componenti del programma di installazione viene restituito dalla proprietà <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-153">Help text on the options supported by individual installer components is returned by the <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="b02c4-154">Le singole opzioni che sono state inserite nella riga di comando sono accessibili a livello di codice dalla proprietà <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-154">The individual options that have been entered on the command line are accessible programmatically from the <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="b02c4-155">Tutte le opzioni e i parametri della riga di comando vengono scritti nel file di log dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-155">All options and command-line parameters are written to the installation log file.</span></span> <span data-ttu-id="b02c4-156">Tuttavia, se si utilizza il parametro `/Password`, che è riconosciuto da alcuni componenti del programma di installazione, le informazioni relative alla password verranno sostituite da otto asterischi (\*) e non verranno visualizzate nel file di log.</span><span class="sxs-lookup"><span data-stu-id="b02c4-156">However, if you use the `/Password` parameter, which is recognized by some installer components, the password information will be replaced by eight asterisks (\*) and will not appear in the log file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b02c4-157">In alcuni casi, i parametri passati al programma di installazione possono includere informazioni riservate o personali che, per impostazione predefinita, vengono scritte in un file di log di testo normale.</span><span class="sxs-lookup"><span data-stu-id="b02c4-157">In some cases, parameters passed to the installer may include sensitive or personally identifiable information, which, by default, is written to a plain text log file.</span></span> <span data-ttu-id="b02c4-158">Per evitare questo comportamento, è possibile eliminare il file di log specificando `/LogFile=` (senza l'argomento *filename*) dopo Installutil.exe nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b02c4-158">To prevent this behavior, you can suppress the log file by specifying `/LogFile=` (with no *filename* argument) after Installutil.exe on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="b02c4-159">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b02c4-159">Remarks</span></span>

<span data-ttu-id="b02c4-160">Le applicazioni .NET Framework sono costituite da file di programma tradizionali e risorse associate, quali code di messaggi, log eventi e contatori delle prestazioni, che è necessario creare quando l'applicazione viene distribuita.</span><span class="sxs-lookup"><span data-stu-id="b02c4-160">.NET Framework applications consist of traditional program files and associated resources, such as message queues, event logs, and performance counters that must be created when the application is deployed.</span></span> <span data-ttu-id="b02c4-161">È possibile utilizzare i componenti del programma di installazione di un assembly per creare queste risorse quando l'applicazione viene installata e rimuoverle quando l'applicazione viene disinstallata.</span><span class="sxs-lookup"><span data-stu-id="b02c4-161">You can use an assembly's installer components to create these resources when your application is installed and to remove them when your application is uninstalled.</span></span> <span data-ttu-id="b02c4-162">Installutil.exe rileva ed esegue questi componenti del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-162">Installutil.exe detects and executes these installer components.</span></span>

<span data-ttu-id="b02c4-163">È possibile specificare più assembly nella stessa riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b02c4-163">You can specify multiple assemblies on the same command line.</span></span> <span data-ttu-id="b02c4-164">Qualsiasi opzione specificata prima del nome di un assembly ha effetto sull'installazione di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="b02c4-164">Any option that occurs before an assembly name applies to that assembly's installation.</span></span> <span data-ttu-id="b02c4-165">Fatta eccezione per `/u` e `/AssemblyName`, le opzioni sono cumulative ma sottoponibili a override.</span><span class="sxs-lookup"><span data-stu-id="b02c4-165">Except for `/u` and `/AssemblyName`, options are cumulative but overridable.</span></span> <span data-ttu-id="b02c4-166">In altre parole, le opzioni specificate per un assembly vengono applicate a tutti gli assembly successivi a meno che l'opzione non venga specificata con un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="b02c4-166">That is, options specified for one assembly apply to all subsequent assemblies unless the option is specified with a new value.</span></span>

<span data-ttu-id="b02c4-167">Se si esegue Installutil.exe su un assembly senza specificare alcuna opzione, i tre file seguenti verranno inseriti nella directory dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="b02c4-167">If you run Installutil.exe against an assembly without specifying any options, it places the following three files into the assembly's directory:</span></span>

- <span data-ttu-id="b02c4-168">InstallUtil.InstallLog - Contiene una descrizione generale dello stato dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-168">InstallUtil.InstallLog - Contains a general description of the installation progress.</span></span>

- <span data-ttu-id="b02c4-169">*assemblyname*.InstallLog: contiene informazioni specifiche della fase di commit del processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-169">*assemblyname*.InstallLog - Contains information specific to the commit phase of the installation process.</span></span> <span data-ttu-id="b02c4-170">Per ulteriori informazioni sulla fase di commit, vedere il metodo <xref:System.Configuration.Install.Installer.Commit%2A>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-170">For more information about the commit phase, see the <xref:System.Configuration.Install.Installer.Commit%2A> method.</span></span>

- <span data-ttu-id="b02c4-171">*assemblyname*.InstallState: contiene i dati usati per disinstallare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b02c4-171">*assemblyname*.InstallState - Contains data used to uninstall the assembly.</span></span>

<span data-ttu-id="b02c4-172">Installutil.exe utilizza la reflection per esaminare gli assembly specificati e individuare tutti i tipi <xref:System.Configuration.Install.Installer> il cui attributo <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-172">Installutil.exe uses reflection to inspect the specified assemblies and to find all <xref:System.Configuration.Install.Installer> types that have the <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> attribute set to `true`.</span></span> <span data-ttu-id="b02c4-173">Lo strumento esegue quindi il metodo <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> o <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> su ciascuna istanza del tipo <xref:System.Configuration.Install.Installer>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-173">The tool then executes either the <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> or the <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> method on each instance of the <xref:System.Configuration.Install.Installer> type.</span></span> <span data-ttu-id="b02c4-174">Installutil.exe esegue l'installazione in modo transazionale: se risulta impossibile installare uno degli assembly, viene eseguito il rollback dell'installazione di tutti gli altri assembly.</span><span class="sxs-lookup"><span data-stu-id="b02c4-174">Installutil.exe performs installation in a transactional manner; that is, if one of the assemblies fails to install, it rolls back the installations of all other assemblies.</span></span> <span data-ttu-id="b02c4-175">La disinstallazione non è invece transazionale.</span><span class="sxs-lookup"><span data-stu-id="b02c4-175">Uninstall is not transactional.</span></span>

<span data-ttu-id="b02c4-176">Installutil.exe può installare o disinstallare assembly con nome sicuro, ma non assembly con firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="b02c4-176">Installutil.exe cannot install or uninstall delay-signed assemblies, but it can install or uninstall strong-named assemblies.</span></span>

<span data-ttu-id="b02c4-177">A partire da .NET Framework versione 2.0, la versione a 32 bit di Common Language Runtime (CLR) viene fornita solo con la versione a 32 bit dello strumento Programma di installazione, mentre la versione a 64 bit di CLR viene fornita con le versioni a 32 bit e a 64 bit di questo strumento.</span><span class="sxs-lookup"><span data-stu-id="b02c4-177">Starting with the .NET Framework version 2.0, the 32-bit version of the common language runtime (CLR) ships with only the 32-bit version of the Installer tool, but the 64-bit version of the CLR ships with both 32-bit and 64-bit versions of the Installer tool.</span></span> <span data-ttu-id="b02c4-178">Se si utilizza CLR a 64 bit, occorre utilizzare lo strumento Programma di installazione a 32 bit per installare assembly a 32 bit e quello a 64 bit per installare assembly a 64 bit e MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="b02c4-178">When using the 64-bit CLR, use the 32-bit Installer tool to install 32-bit assemblies, and the 64-bit Installer tool to install 64-bit and Microsoft intermediate language (MSIL) assemblies.</span></span> <span data-ttu-id="b02c4-179">Il funzionamento delle due versioni dello strumento Programma di installazione è identico.</span><span class="sxs-lookup"><span data-stu-id="b02c4-179">Both versions of the Installer tool behave the same.</span></span>

<span data-ttu-id="b02c4-180">Non è possibile utilizzare Installutil.exe per distribuire un servizio di Windows creato utilizzando C++ perché Installutil.exe non è in grado di riconoscere il codice nativo incorporato generato dal compilatore C++.</span><span class="sxs-lookup"><span data-stu-id="b02c4-180">You cannot use Installutil.exe to deploy a Windows service that was created by using C++, because Installutil.exe cannot recognize the embedded native code that is produced by the C++ compiler.</span></span> <span data-ttu-id="b02c4-181">Se si tenta di distribuire un servizio di Windows C++ con Installutil.exe, verrà generata un'eccezione quale <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="b02c4-181">If you try to deploy a C++ Windows service with Installutil.exe, an exception such as <xref:System.BadImageFormatException> will be thrown.</span></span> <span data-ttu-id="b02c4-182">Per operare con questo scenario, spostare il codice del servizio in un modulo C++, quindi scrivere l'oggetto del programma di installazione in C# o in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b02c4-182">To work with this scenario, move the service code to a C++ module, and then write the installer object in C# or Visual Basic.</span></span>

## <a name="examples"></a><span data-ttu-id="b02c4-183">Esempi</span><span class="sxs-lookup"><span data-stu-id="b02c4-183">Examples</span></span>

<span data-ttu-id="b02c4-184">Il comando che segue visualizza una descrizione della sintassi e delle opzioni di comando per InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="b02c4-184">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span>

```console
installutil /?
```

<span data-ttu-id="b02c4-185">Il comando che segue visualizza una descrizione della sintassi e delle opzioni di comando per InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="b02c4-185">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="b02c4-186">Visualizza anche una descrizione e un elenco delle opzioni supportate dai componenti del programma di installazione in `myAssembly.exe` se il testo della Guida è stato assegnato alla proprietà <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="b02c4-186">It also displays a description and list of options supported by the installer components in `myAssembly.exe` if help text has been assigned to the installer's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span>

```console
installutil /? myAssembly.exe
```

<span data-ttu-id="b02c4-187">Il comando che segue esegue i componenti del programma di installazione nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-187">The following command executes the installer components in the assembly `myAssembly.exe`.</span></span>

```console
installutil myAssembly.exe
```

<span data-ttu-id="b02c4-188">Il comando che segue esegue i componenti del programma di installazione in un assembly utilizzando l'opzione `/AssemblyName` e un nome completo.</span><span class="sxs-lookup"><span data-stu-id="b02c4-188">The following command executes the installer components in an assembly by using the `/AssemblyName` switch and a fully qualified name.</span></span>

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="b02c4-189">Il comando che segue esegue i componenti del programma di installazione in un assembly specificato in base al nome file e in un assembly specificato in base al nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b02c4-189">The following command executes the installer components in an assembly specified by file name and in an assembly specified by strong name.</span></span> <span data-ttu-id="b02c4-190">Si noti che tutti gli assembly specificati in base al nome file devono precedere gli assembly specificati in base al nome sicuro nella riga di comando, poiché l'opzione `/AssemblyName` non può essere sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="b02c4-190">Note that all assemblies specified by file name must precede assemblies specified by strong name on the command line, because the `/AssemblyName` option cannot be overridden.</span></span>

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="b02c4-191">Il comando che segue esegue i componenti del programma di disinstallazione nell'assembly `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-191">The following command executes the uninstaller components in the assembly `myAssembly.exe`.</span></span>

```console
installutil /u myAssembly.exe
```

<span data-ttu-id="b02c4-192">Il comando seguente esegue i componenti del programma di disinstallazione negli assembly `myAssembly1.exe` e `myAssembly2.exe`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-192">The following command executes the uninstaller components in the assemblies `myAssembly1.exe` and `myAssembly2.exe`.</span></span>

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

<span data-ttu-id="b02c4-193">Poiché la posizione dell'opzione `/u` nella riga di comando non è importante, questo è equivalente al comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b02c4-193">Because the position of the `/u` option on the command line is not important, this is equivalent to the following command.</span></span>

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

<span data-ttu-id="b02c4-194">Il comando che segue esegue i programmi di installazione nell'assembly `myAssembly.exe` e specifica che le informazioni sullo stato verranno scritte in `myLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-194">The following command executes the installers in the assembly `myAssembly.exe` and specifies that progress information will be written to `myLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

<span data-ttu-id="b02c4-195">Il comando che segue esegue i programmi di installazione contenuti nell'assembly `myAssembly.exe`, specifica che le informazioni sullo stato di avanzamento devono essere scritte in `myLog.InstallLog` e utilizza l'opzione `/reg` personalizzata dei programmi di installazione per specificare che è necessario aggiornare il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b02c4-195">The following command executes the installers in the assembly `myAssembly.exe`, specifies that progress information should be written to `myLog.InstallLog`, and uses the installers' custom `/reg` option to specify that updates should be made to the system registry.</span></span>

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

<span data-ttu-id="b02c4-196">Il comando seguente esegue i programmi di installazione contenuti nell'assembly `myAssembly.exe`, usa l'opzione `/email` personalizzata del programma di installazione per specificare l'indirizzo di posta elettronica dell'utente ed elimina l'output nel file di log.</span><span class="sxs-lookup"><span data-stu-id="b02c4-196">The following command executes the installers in the assembly `myAssembly.exe`, uses the installer's custom `/email` option to specify the user's email address, and suppresses output to the log file.</span></span>

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

<span data-ttu-id="b02c4-197">Il comando che segue scrive lo stato dell'installazione di `myAssembly.exe` in `myLog.InstallLog` e quello di `myTestAssembly.exe` in `myTestLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="b02c4-197">The following command writes the installation progress for `myAssembly.exe` to `myLog.InstallLog` and writes the progress for `myTestAssembly.exe` to `myTestLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a><span data-ttu-id="b02c4-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b02c4-198">See also</span></span>

- <xref:System.Configuration.Install>
- [<span data-ttu-id="b02c4-199">Strumenti</span><span class="sxs-lookup"><span data-stu-id="b02c4-199">Tools</span></span>](index.md)
- [<span data-ttu-id="b02c4-200">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b02c4-200">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
