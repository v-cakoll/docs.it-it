---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: a977bc4cff822de551bf82d0f31707e9b2b6ea41
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348542"
---
# <a name="-subsystemversion-visual-basic"></a>-subsystemversion (Visual Basic)

Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, determinando le versioni di Windows in cui è possibile eseguire il file eseguibile. In genere, questa opzione assicura che il file eseguibile possa sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.

> [!NOTE]
> Per specificare il sottosistema stesso, usare l'opzione del compilatore [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).

## <a name="syntax"></a>Sintassi

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a>Parametri

`major.minor`

Versione minima richiesta per il sottosistema, espressa in una notazione del punto per le versioni principali e secondarie. Ad esempio, è possibile specificare che un'applicazione non può essere eseguita su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento. È necessario specificare i valori per `major` e `minor` come numeri interi.

Gli zeri iniziali della versione `minor` non modificano la versione, a differenza degli zeri finali. Ad esempio, 6.1 e 6.01 si fanno riferimento alla stessa versione, ma 6.10 fa riferimento a una versione diversa. È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.

## <a name="remarks"></a>Note

Nella tabella seguente sono elencate le versioni comuni del sottosistema di Windows.

|Versione di Windows|Versione del sottosistema|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|

## <a name="default-values"></a>Valori predefiniti

Il valore predefinito dell'opzione del compilatore **-subsystemversion** dipende dalle condizioni elencate di seguito:

- Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:

  - [/target:appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)

  - [/target:winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)

  - [-platform:arm](../../../visual-basic/reference/command-line-compiler/platform.md)

- Il valore predefinito è 6.00 se si usa MSBuild, se la destinazione è .NET Framework 4.5 e se non è stata impostata una delle opzioni del compilatore specificate in precedenza in questo elenco.

- Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.

## <a name="setting-this-option"></a>Impostazione di questa opzione

To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML. Non è possibile impostare questa opzione nell'IDE di Visual Studio. Per altre informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [Proprietà di progetto MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)

- [Proprietà di MSBuild](/visualstudio/msbuild/msbuild-properties)
