---
title: Attivare il completamento con tasto TAB
description: Questo articolo illustra come abilitare il completamento tramite tasto TAB nell'interfaccia della riga di comando di .NET Core per PowerShell, Bash e zsh.
author: adegeo
ms.author: adegeo
ms.date: 11/03/2019
ms.openlocfilehash: 491e1ca34c20c3994a571fc2deff7392c6bdb3f2
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324385"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a><span data-ttu-id="64651-103">Come abilitare il completamento tramite TAB per l'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="64651-103">How to enable TAB completion for the .NET Core CLI</span></span>

<span data-ttu-id="64651-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="64651-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="64651-105">Questo articolo descrive come configurare il completamento tramite TAB per tre shell: PowerShell, Bash e zsh.</span><span class="sxs-lookup"><span data-stu-id="64651-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="64651-106">Per altre shell, fare riferimento alla relativa documentazione per informazioni su come configurare il completamento tramite tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="64651-106">For other shells, refer to their documentation on how to configure tab completion.</span></span>

<span data-ttu-id="64651-107">Una volta configurato, il completamento tramite tasto TAB per la interfaccia della riga di comando di .NET Core viene attivato digitando un `dotnet` comando nella shell, quindi premendo il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="64651-107">Once set up, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="64651-108">La riga di comando corrente viene inviata al comando `dotnet complete` e i risultati vengono elaborati dalla shell.</span><span class="sxs-lookup"><span data-stu-id="64651-108">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="64651-109">Per testare i risultati senza abilitazione del completamento tramite TAB, inviare direttamente un elemento al comando `dotnet complete`.</span><span class="sxs-lookup"><span data-stu-id="64651-109">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="64651-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64651-110">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="64651-111">Se questo comando non funziona, assicurarsi che sia installato .NET Core 2.0 SDK o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="64651-111">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="64651-112">Se è installata la versione appropriata ma il comando non funziona, assicurarsi che il comando `dotnet` risolva in .NET Core 2.0 SDK o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="64651-112">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="64651-113">Usare il comando `dotnet --version` per verificare la versione di `dotnet` in cui risolve il percorso corrente.</span><span class="sxs-lookup"><span data-stu-id="64651-113">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="64651-114">Per altre informazioni, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="64651-114">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="64651-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="64651-115">Examples</span></span>

<span data-ttu-id="64651-116">Gli esempi seguenti visualizzano risultati del completamento tramite TAB:</span><span class="sxs-lookup"><span data-stu-id="64651-116">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="64651-117">Input</span><span class="sxs-lookup"><span data-stu-id="64651-117">Input</span></span>                                | <span data-ttu-id="64651-118">diventa</span><span class="sxs-lookup"><span data-stu-id="64651-118">becomes</span></span>                                                                     | <span data-ttu-id="64651-119">perché</span><span class="sxs-lookup"><span data-stu-id="64651-119">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="64651-120">`add` è il primo sottocomando in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="64651-120">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="64651-121">Il completamento tramite TAB rileva la corrispondenza delle sottostringhe e `--help` viene per prima in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="64651-121">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="64651-122">Se si preme TAB una seconda volta, viene visualizzato il suggerimento successivo.</span><span class="sxs-lookup"><span data-stu-id="64651-122">Pressing tab a second time brings up the next suggestion.</span></span>
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="64651-123">I risultati vengono restituiti in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="64651-123">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="64651-124">Il completamento tramite TAB è compatibile con i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="64651-124">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="64651-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64651-125">PowerShell</span></span>

<span data-ttu-id="64651-126">Per aggiungere il completamento tramite TAB a **PowerShell** per l'interfaccia della riga di comando di .NET Core, creare o modificare il profilo memorizzato nella variabile `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="64651-126">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="64651-127">Per altre informazioni, vedere [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) (Come creare un profilo) e [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy) (Profili e criteri di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="64651-127">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span>

<span data-ttu-id="64651-128">Aggiungere il codice seguente al profilo:</span><span class="sxs-lookup"><span data-stu-id="64651-128">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="64651-129">bash</span><span class="sxs-lookup"><span data-stu-id="64651-129">bash</span></span>

<span data-ttu-id="64651-130">Per aggiungere il completamento tramite TAB alla shell **bash** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.bashrc`:</span><span class="sxs-lookup"><span data-stu-id="64651-130">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="64651-131">zsh</span><span class="sxs-lookup"><span data-stu-id="64651-131">zsh</span></span>

<span data-ttu-id="64651-132">Per aggiungere il completamento tramite TAB alla shell **zsh** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.zshrc`:</span><span class="sxs-lookup"><span data-stu-id="64651-132">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
