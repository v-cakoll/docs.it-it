---
title: -delaysign (opzioni del compilatore C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970437"
---
# <a name="-delaysign-c-compiler-options"></a>-delaysign (opzioni del compilatore C#)

Questa opzione indica al compilatore di riservare spazio nel file di output in modo che si possa aggiungere una firma digitale in un secondo tempo.

## <a name="syntax"></a>Sintassi

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a>Argomenti

`+` &#124; `-`

Usare **-delaysign-** se si vuole un assembly con firma completa. Usare **-delaysign+** se si vuole solo inserire la chiave pubblica nell'assembly. L'impostazione predefinita è **-delaysign-**.

## <a name="remarks"></a>Osservazioni

L'opzione **-delaysign** non ha alcun effetto se non utilizzata con [-keyfile](./keyfile-compiler-option.md) o [-keycontainer](./keycontainer-compiler-option.md).

Le opzioni **-delaysign** e **-publicsign** si escludono a vicenda.

Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata. Tale operazione crea una firma digitale archiviata nel file contenente il manifesto. Quando per un assembly è impostata la firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta successivamente.

Ad esempio, l'uso di **-delaysign+** consente a un tester di inserire l'assembly nella Global Assembly Cache. Al termine del test, è possibile firmare completamente l'assembly inserendo la chiave privata nell'assembly con l'utilità [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md).

Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) e [Ritardo della firma di un assembly](../../../standard/assembly/delay-sign.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio

1. Aprire la pagina **Proprietà** del progetto.
1. Modificare la proprietà **Solo firma ritardata**.

Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.

## <a name="see-also"></a>Vedere anche

- [Opzione -publicsign C#](publicsign-compiler-option.md)
- [Opzioni del compilatore C](index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
