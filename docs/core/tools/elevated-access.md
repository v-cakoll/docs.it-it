---
title: Accesso con privilegi elevati per comandi dotnet
description: Informazioni sulle procedure consigliate per comandi dotnet che richiedono l'accesso con privilegi elevati.
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: 1cf29012736e5b6d858ca22dc2a9b97e7e8e33ef
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503575"
---
# <a name="elevated-access-for-dotnet-commands"></a><span data-ttu-id="cb4fc-103">Accesso con privilegi elevati per comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="cb4fc-103">Elevated access for dotnet commands</span></span>

<span data-ttu-id="cb4fc-104">Le procedure consigliate per lo sviluppo di software supportano gli sviluppatori nella scrittura di software con una richiesta minima di privilegi.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-104">Software development best practices guide developers to writing software that requires the least amount of privilege.</span></span> <span data-ttu-id="cb4fc-105">Per alcuni software, ad esempio gli strumenti di monitoraggio delle prestazioni, è però necessaria un'autorizzazione di amministratore a causa delle regole del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-105">However, some software, like performance monitoring tools, requires admin permission because of operating system rules.</span></span> <span data-ttu-id="cb4fc-106">Questo documento descrive gli scenari supportati per la scrittura di questo tipo di software usando .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-106">The following guidance describes supported scenarios for writing such software with .NET Core.</span></span> 

<span data-ttu-id="cb4fc-107">I comandi seguenti possono essere eseguiti con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-107">The following commands can be run elevated:</span></span>

- <span data-ttu-id="cb4fc-108">Comandi `dotnet tool`, ad esempio [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="cb4fc-108">`dotnet tool` commands, such as [dotnet tool install](dotnet-tool-install.md).</span></span>
- `dotnet run --no-build`

<span data-ttu-id="cb4fc-109">Non è consigliabile eseguire altri comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-109">We don't recommend running other commands elevated.</span></span> <span data-ttu-id="cb4fc-110">In particolare, non è consigliabile elevare i privilegi con comandi che usano MSBuild, ad esempio [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md) e [dotnet run](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="cb4fc-110">In particular, we don't recommend elevation with commands that use MSBuild, such as [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md), and [dotnet run](dotnet-run.md).</span></span> <span data-ttu-id="cb4fc-111">Il problema principale è la gestione delle autorizzazioni, quando un utente passa da account radice ad account con restrizioni dopo l'invio di comandi dotnet.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-111">The primary issue is permission management problems when a user transitions back and forth between root and a restricted account after issuing dotnet commands.</span></span> <span data-ttu-id="cb4fc-112">Può succedere che un utente con restrizioni non acceda al file creato da un utente ROOT.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-112">You may find as a restricted user that you don't have access to the file built by a root user.</span></span> <span data-ttu-id="cb4fc-113">Questa situazione può essere risolta in diversi modi che non è necessario analizzare per primi.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-113">There are ways to resolve this situation, but they're unnecessary to get into in the first place.</span></span>

<span data-ttu-id="cb4fc-114">È possibile eseguire comandi come radice, purché l'utente non passi da account radice ad account con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-114">You can run commands as root as long as you don’t transition back and forth between root and a restricted account.</span></span> <span data-ttu-id="cb4fc-115">I contenitori Docker vengono ad esempio eseguiti come radice per impostazione predefinita, pertanto hanno questa caratteristica.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-115">For example, Docker containers run as root by default, so they have this characteristic.</span></span>

## <a name="global-tool-installation"></a><span data-ttu-id="cb4fc-116">Installazione dello strumento globale</span><span class="sxs-lookup"><span data-stu-id="cb4fc-116">Global tool installation</span></span>

<span data-ttu-id="cb4fc-117">Le istruzioni seguenti illustrano il modo consigliato per installare, eseguire e disinstallare gli strumenti per .NET Core che per essere eseguiti richiedono autorizzazioni con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-117">The following instructions demonstrate the recommended way to install, run, and uninstall .NET Core tools that require elevated permissions to execute.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="cb4fc-118">Windows</span><span class="sxs-lookup"><span data-stu-id="cb4fc-118">Windows</span></span>](#tab/windows)

### <a name="install-the-global-tool"></a><span data-ttu-id="cb4fc-119">Installare lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="cb4fc-119">Install the global tool</span></span>

<span data-ttu-id="cb4fc-120">Se la cartella `%ProgramFiles%\dotnet-tools` è già esistente, eseguire le operazioni seguenti per verificare se il gruppo "Utenti" dispone dell'autorizzazione per scrivere o modificare tale directory:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-120">If the folder `%ProgramFiles%\dotnet-tools` already exists, do the following to check whether the "Users" group has permission to write or modify that directory:</span></span>

- <span data-ttu-id="cb4fc-121">Fare clic con il pulsante destro del mouse sulla cartella `%ProgramFiles%\dotnet-tools` e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-121">Right-click the `%ProgramFiles%\dotnet-tools` folder and select **Properties**.</span></span> <span data-ttu-id="cb4fc-122">Verrà visualizzata la finestra di dialogo **Proprietà comuni**.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-122">The **Common Properties** dialog box opens.</span></span> 
- <span data-ttu-id="cb4fc-123">Selezionare la scheda **sicurezza** . In utenti e **gruppi**controllare se il gruppo "utenti" dispone dell'autorizzazione per scrivere o modificare la directory.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-123">Select the **Security** tab. Under **Group or user names**, check whether the “Users” group has permission to write or modify the directory.</span></span> 
- <span data-ttu-id="cb4fc-124">Se il gruppo "Utenti" è autorizzato alla scrittura o alla modifica della directory, usare un nome di directory diverso quando si installano gli strumenti anziché usare *dotnet-tools*.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-124">If the "Users" group can write or modify the directory, use a different directory name when installing the tools rather than *dotnet-tools*.</span></span>

<span data-ttu-id="cb4fc-125">Per installare gli strumenti, eseguire il comando seguente al prompt con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-125">To install tools, run the following command in elevated prompt.</span></span> <span data-ttu-id="cb4fc-126">Verrà creata la cartella *dotnet-tools* durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-126">It will create the *dotnet-tools* folder during the installation.</span></span>

```dotnetcli
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a><span data-ttu-id="cb4fc-127">Eseguire lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="cb4fc-127">Run the global tool</span></span>

<span data-ttu-id="cb4fc-128">**Opzione 1**: usare il percorso completo al prompt con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-128">**Option 1** Use the full path with elevated prompt:</span></span>

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

<span data-ttu-id="cb4fc-129">**Opzione 2**: aggiungere la cartella appena creata a `%Path%`.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-129">**Option 2** Add the newly created folder to `%Path%`.</span></span> <span data-ttu-id="cb4fc-130">È necessario eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-130">You only need to do this operation once.</span></span>

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

<span data-ttu-id="cb4fc-131">Eseguire con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-131">And run with:</span></span>

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="cb4fc-132">Disinstallare lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="cb4fc-132">Uninstall the global tool</span></span>

<span data-ttu-id="cb4fc-133">Al prompt con privilegi elevati digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-133">In an elevated prompt, type the following command:</span></span>

```dotnetcli
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linux"></a>[<span data-ttu-id="cb4fc-134">Linux</span><span class="sxs-lookup"><span data-stu-id="cb4fc-134">Linux</span></span>](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macos"></a>[<span data-ttu-id="cb4fc-135">macOS</span><span class="sxs-lookup"><span data-stu-id="cb4fc-135">macOS</span></span>](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a><span data-ttu-id="cb4fc-136">Strumenti locali</span><span class="sxs-lookup"><span data-stu-id="cb4fc-136">Local tools</span></span>

<span data-ttu-id="cb4fc-137">L'ambito degli strumenti locali è definito in base ad albero di sottodirectory e utente.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-137">Local tools are scoped per subdirectory tree, per user.</span></span> <span data-ttu-id="cb4fc-138">Quando vengono eseguiti con privilegi elevati, gli strumenti locali condividono un ambiente utente con restrizioni nell'ambiente con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-138">When run elevated, local tools share a restricted user environment to the elevated environment.</span></span> <span data-ttu-id="cb4fc-139">In Linux e macOS i file vengono di conseguenza impostati con accesso riservato solo all'utente ROOT.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-139">In Linux and macOS, this results in files being set with root user-only access.</span></span> <span data-ttu-id="cb4fc-140">Se l'utente passa nuovamente a un account con restrizioni, l'utente non potrà più accedere o scrivere i file.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-140">If the user switches back to a restricted account, the user can no longer access or write to the files.</span></span> <span data-ttu-id="cb4fc-141">Non è quindi consigliato installare strumenti che richiedono elevazione come gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-141">So installing tools that require elevation as local tools isn't recommended.</span></span> <span data-ttu-id="cb4fc-142">Usare invece l'opzione `--tool-path` e seguire le linee guida precedenti per gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-142">Instead, use the `--tool-path` option and the previous guidelines for global tools.</span></span>

## <a name="elevation-during-development"></a><span data-ttu-id="cb4fc-143">Elevazione durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="cb4fc-143">Elevation during development</span></span>

<span data-ttu-id="cb4fc-144">Durante lo sviluppo potrebbe essere necessario l'accesso con privilegi elevati per testare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-144">During development, you may need elevated access to test your application.</span></span> <span data-ttu-id="cb4fc-145">Questo scenario è ad esempio comune per le app IoT.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-145">This scenario is common for IoT apps, for example.</span></span> <span data-ttu-id="cb4fc-146">È consigliabile compilare l'applicazione senza elevazione ed eseguirla poi elevando i privilegi.</span><span class="sxs-lookup"><span data-stu-id="cb4fc-146">We recommend that you build the application without elevation and then run it with elevation.</span></span> <span data-ttu-id="cb4fc-147">Esistono alcuni modelli come quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-147">There are a few patterns, as follows:</span></span>

- <span data-ttu-id="cb4fc-148">Uso di un eseguibile generato, che offre le prestazioni migliori in fase di avvio:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-148">Using generated executable (it provides the best startup performance):</span></span>

   ```dotnetcli
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```
    
- <span data-ttu-id="cb4fc-149">Uso del comando [dotnet run](dotnet-run.md) con il flag `—no-build` per evitare di generare nuovi file binari:</span><span class="sxs-lookup"><span data-stu-id="cb4fc-149">Using the [dotnet run](dotnet-run.md) command with the `—no-build` flag to avoid generating new binaries:</span></span>

   ```dotnetcli
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a><span data-ttu-id="cb4fc-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb4fc-150">See also</span></span>

- [<span data-ttu-id="cb4fc-151">Panoramica degli strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb4fc-151">.NET Core Global Tools overview</span></span>](global-tools.md)
