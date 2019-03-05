---
title: Abilitare il completamento tramite TAB
description: Questo articolo illustra come abilitare il completamento tramite tasto TAB nell'interfaccia della riga di comando di .NET Core per PowerShell, Bash e zsh.
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: 16574e02aa9f9167602401eef2ad7a73e07ad107
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203337"
---
# <a name="how-to-enable-tab-completion-for-net-core-cli"></a><span data-ttu-id="1ef05-103">Come abilitare il completamento tramite TAB per l'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1ef05-103">How to enable TAB completion for .NET Core CLI</span></span>

<span data-ttu-id="1ef05-104">A partire da .NET Core 2.0 SDK, l'interfaccia della riga di comando di .NET Core supporta il completamento tramite TAB.</span><span class="sxs-lookup"><span data-stu-id="1ef05-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="1ef05-105">Questo articolo descrive come configurare il completamento tramite TAB per tre shell: PowerShell, Bash e zsh.</span><span class="sxs-lookup"><span data-stu-id="1ef05-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="1ef05-106">È possibile che il completamento automatico sia supportato anche in altre shell.</span><span class="sxs-lookup"><span data-stu-id="1ef05-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="1ef05-107">Fare riferimento alla documentazione di tali shell per configurare il completamento automatico. I passaggi dovrebbero essere simili a quelli descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1ef05-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="1ef05-108">Dopo la configurazione, il completamento tramite TAB per l'interfaccia della riga di comando di .NET Core può essere attivato digitando un comando `dotnet` nella shell e quindi premendo il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="1ef05-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="1ef05-109">La riga di comando corrente viene inviata al comando `dotnet complete` e i risultati vengono elaborati dalla shell.</span><span class="sxs-lookup"><span data-stu-id="1ef05-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="1ef05-110">Per testare i risultati senza abilitazione del completamento tramite TAB, inviare direttamente un elemento al comando `dotnet complete`.</span><span class="sxs-lookup"><span data-stu-id="1ef05-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="1ef05-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1ef05-111">For example:</span></span>

```
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="1ef05-112">Se questo comando non funziona, assicurarsi che sia installato .NET Core 2.0 SDK o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="1ef05-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="1ef05-113">Se è installata la versione appropriata ma il comando non funziona, assicurarsi che il comando `dotnet` risolva in .NET Core 2.0 SDK o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1ef05-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="1ef05-114">Usare il comando `dotnet --version` per verificare la versione di `dotnet` in cui risolve il percorso corrente.</span><span class="sxs-lookup"><span data-stu-id="1ef05-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="1ef05-115">Per altre informazioni, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="1ef05-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="1ef05-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="1ef05-116">Examples</span></span>

<span data-ttu-id="1ef05-117">Gli esempi seguenti visualizzano risultati del completamento tramite TAB:</span><span class="sxs-lookup"><span data-stu-id="1ef05-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="1ef05-118">Input</span><span class="sxs-lookup"><span data-stu-id="1ef05-118">Input</span></span>                                | <span data-ttu-id="1ef05-119">diventa</span><span class="sxs-lookup"><span data-stu-id="1ef05-119">becomes</span></span>                                                                     | <span data-ttu-id="1ef05-120">perché</span><span class="sxs-lookup"><span data-stu-id="1ef05-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="1ef05-121">`add` è il primo sottocomando in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="1ef05-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="1ef05-122">Il completamento tramite TAB rileva la corrispondenza delle sottostringhe e `--help` viene per prima in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="1ef05-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="1ef05-123">Se si preme TAB una seconda volta, viene visualizzato il suggerimento successivo.</span><span class="sxs-lookup"><span data-stu-id="1ef05-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="1ef05-124">I risultati vengono restituiti in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="1ef05-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="1ef05-125">Il completamento tramite TAB è compatibile con i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1ef05-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="1ef05-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ef05-126">PowerShell</span></span>

<span data-ttu-id="1ef05-127">Per aggiungere il completamento tramite TAB a **PowerShell** per l'interfaccia della riga di comando di .NET Core, creare o modificare il profilo memorizzato nella variabile `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="1ef05-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="1ef05-128">Per altre informazioni, vedere [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) (Come creare un profilo) e [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy) (Profili e criteri di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="1ef05-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="1ef05-129">Aggiungere il codice seguente al profilo:</span><span class="sxs-lookup"><span data-stu-id="1ef05-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="1ef05-130">Bash</span><span class="sxs-lookup"><span data-stu-id="1ef05-130">Bash</span></span>

<span data-ttu-id="1ef05-131">Per aggiungere il completamento tramite TAB alla shell **bash** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.bashrc`:</span><span class="sxs-lookup"><span data-stu-id="1ef05-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="1ef05-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="1ef05-132">Zsh</span></span>

<span data-ttu-id="1ef05-133">Per aggiungere il completamento tramite TAB alla shell **zsh** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.zshrc`:</span><span class="sxs-lookup"><span data-stu-id="1ef05-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
