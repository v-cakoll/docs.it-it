---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: ad8a2b5fc87dd7beee86d96331cf3961315be533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345082"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (opzioni del compilatore C#)

**-nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi di sistema.

## <a name="syntax"></a>Sintassi

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Osservazioni

Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.

Se non si specifica **-nostdlib**, mscorlib.dll viene importata nel programma (equivale a specificare **-nostdlib-**). Specificare **-nostdlib** equivale a specificare **-nostdlib+**.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Per impostare questa opzione del compilatore in Visual Studio

> [!NOTE]
> Le istruzioni seguenti si applicano solo a Visual Studio 2015 (e versioni precedenti). La proprietà di compilazione Non fare **riferimento a mscorlib.dll** non esiste nelle versioni più recenti di Visual Studio.

1. Aprire la pagina **Proprietà** del progetto.

2. Fare clic sulla pagina di proprietà **Compilazione** .

3. Fare clic sul pulsante **Avanzate**.

4. Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .

### <a name="to-set-this-compiler-option-programmatically"></a>Per impostare l'opzione del compilatore a livello di codice

Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
