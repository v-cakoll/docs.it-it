---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935524"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (opzioni del compilatore C#)

**-nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi di sistema.

## <a name="syntax"></a>Sintassi

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Note

Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.

Se non si specifica **-nostdlib**, mscorlib.dll viene importata nel programma (equivale a specificare **-nostdlib-**). Specificare **-nostdlib** equivale a specificare **-nostdlib+**.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Per impostare questa opzione del compilatore in Visual Studio

> [!NOTE]
> Le istruzioni seguenti si applicano solo a Visual Studio 2015 (e versioni precedenti). La proprietà di compilazione **Ometti riferimenti a mscorlib.dll** non esiste in Visual Studio 2017.

1. Aprire la pagina **Proprietà** del progetto.

2. Fare clic sulla pagina di proprietà **Compilazione** .

3. Fare clic su **Avanzate** .

4. Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .

### <a name="to-set-this-compiler-option-programmatically"></a>Per impostare l'opzione del compilatore a livello di codice

Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
