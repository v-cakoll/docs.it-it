---
title: Abilitare il completamento tramite TAB
description: Questo articolo illustra come abilitare il completamento tramite tasto TAB nell'interfaccia della riga di comando di .NET Core per PowerShell, Bash e zsh.
author: thraka
ms.author: adegeo
ms.date: 11/03/2019
ms.openlocfilehash: 649b723c2abfa74443a16914594284a77e0eafc0
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920539"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a>Come abilitare il completamento tramite TAB per l'interfaccia della riga di comando di .NET Core

A partire da .NET Core 2.0 SDK, l'interfaccia della riga di comando di .NET Core supporta il completamento tramite TAB. Questo articolo descrive come configurare il completamento tramite TAB per tre shell: PowerShell, Bash e zsh. È possibile che il completamento automatico sia supportato anche in altre shell. Fare riferimento alla documentazione di tali shell per configurare il completamento automatico. I passaggi dovrebbero essere simili a quelli descritti in questo articolo.

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

Dopo la configurazione, il completamento tramite TAB per l'interfaccia della riga di comando di .NET Core può essere attivato digitando un comando `dotnet` nella shell e quindi premendo il tasto TAB. La riga di comando corrente viene inviata al comando `dotnet complete` e i risultati vengono elaborati dalla shell. Per testare i risultati senza abilitazione del completamento tramite TAB, inviare direttamente un elemento al comando `dotnet complete`. Ad esempio:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

Se questo comando non funziona, assicurarsi che sia installato .NET Core 2.0 SDK o versioni successive. Se è installata la versione appropriata ma il comando non funziona, assicurarsi che il comando `dotnet` risolva in .NET Core 2.0 SDK o una versione successiva. Usare il comando `dotnet --version` per verificare la versione di `dotnet` in cui risolve il percorso corrente. Per altre informazioni, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md).

### <a name="examples"></a>Esempi

Gli esempi seguenti visualizzano risultati del completamento tramite TAB:

Input                                | diventa                                                                     | perché
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | `add` è il primo sottocomando in ordine alfabetico.
`dotnet add p⇥`                      | `dotnet add --help`                                                          | Il completamento tramite TAB rileva la corrispondenza delle sottostringhe e `--help` viene per prima in ordine alfabetico.
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | Se si preme TAB una seconda volta, viene visualizzato il suggerimento successivo.      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | I risultati vengono restituiti in ordine alfabetico.
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | Il completamento tramite TAB è compatibile con i file di progetto.

## <a name="powershell"></a>PowerShell

Per aggiungere il completamento tramite TAB a **PowerShell** per l'interfaccia della riga di comando di .NET Core, creare o modificare il profilo memorizzato nella variabile `$PROFILE`. Per altre informazioni, vedere [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) (Come creare un profilo) e [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy) (Profili e criteri di esecuzione). 

Aggiungere il codice seguente al profilo:

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a>barra rovesciata

Per aggiungere il completamento tramite TAB alla shell **bash** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.bashrc`:

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

## <a name="zsh"></a>zsh

Per aggiungere il completamento tramite TAB alla shell **zsh** per l'interfaccia della riga di comando di .NET Core, aggiungere il codice seguente al file `.zshrc`:

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
