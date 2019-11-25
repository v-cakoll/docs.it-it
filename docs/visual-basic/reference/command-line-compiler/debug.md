---
title: /debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 3beb9ad3829c2f55120a9136e6e54185551bd20b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344783"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

Causes the compiler to generate debugging information and place it in the output file(s).

## <a name="syntax"></a>Sintassi

```console
-debug[+ | -]
```

Oppure

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>argomenti

|Termine|Definizione|
|---|---|
|`+` &#124; `-`|Parametro facoltativo. Specifying `+` or `/debug` causes the compiler to generate debugging information and place it in a .pdb file. Specifying `-` has the same effect as not specifying `/debug`.|
|`full` &#124; `pdbonly`|Parametro facoltativo. Specifica il tipo di informazioni di debug generate dal compilatore. If you do not specify `/debug:pdbonly`, the default is `full`, which enables you to attach a debugger to the running program. The `pdbonly` argument allows source-code debugging when the program is started in the debugger, but it displays assembly-language code only when the running program is attached to the debugger.|

## <a name="remarks"></a>Note

Usare questa opzione per creare build di debug. If you do not specify `/debug`, `/debug+`, or `/debug:full`, you will be unable to debug the output file of your program.

By default, debugging information is not emitted (`/debug-`). To emit debugging information, specify `/debug` or `/debug+`.

Per informazioni su come configurare le prestazioni di debug di un'applicazione, vedere [Semplificazione del debug di un'immagine](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|To set -debug in the Visual Studio integrated development environment|
|---|
|1.  With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**. <br />2.  Click the **Compile** tab.<br />3.  Click **Advanced Compile Options**.<br />4.  Modify the value in the **Generate Debug Info** box.|

## <a name="example"></a>Esempio

The following example puts debugging information in output file `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
