---
title: -publicsign (opzioni del compilatore C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: de7d9c98b0f279b52bc93711c5b986a2b2e57215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61662530"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (opzioni del compilatore C#)

Questa opzione indica al compilatore di applicare una chiave pubblica ma non firma effettivamente l'assembly. L'opzione **-publicsign** imposta anche un bit nell'assembly che indica al runtime che il file è effettivamente firmato.

## <a name="syntax"></a>Sintassi

```console
-publicsign
```

## <a name="arguments"></a>Argomenti

No.

## <a name="remarks"></a>Osservazioni

L'opzione **-publicsign** richiede l'uso di [-keyfile](keyfile-compiler-option.md) o [-keycontainer](keycontainer-compiler-option.md). Le opzioni **keyfile** o **keycontainer** specificano la chiave pubblica.

Le opzioni **-publicsign** e **-delaysign** si escludono a vicenda.

Talvolta denominata "firma falsa" o "firma OSS", la firma pubblica include la chiave pubblica in un assembly di output e imposta il flag "firmato", ma non firma effettivamente l'assembly con una chiave privata. Ciò è utile per progetti open source in cui le persone devono poter compilare assembly compatibili con gli assembly rilasciati con "firma completa", ma non hanno accesso alla chiave privata usata per firmare gli assembly. Dato che praticamente nessun consumer ha effettivamente la necessità di verificare se l'assembly è firmato completamente, questi assembly compilati pubblicamente sono utilizzabili in quasi tutti gli scenari in cui verrebbe usato un assembly con firma completa.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio

1. Aprire la pagina **Proprietà** del progetto.
1. Modificare la proprietà **Solo firma ritardata**.

## <a name="see-also"></a>Vedere anche

- [Opzione -delaysign del compilatore C#](delaysign-compiler-option.md)
- [Opzione -keyfile del compilatore C#](keyfile-compiler-option.md)
- [Opzione -keycontainer del compilatore C#](keycontainer-compiler-option.md)
- [Opzioni del compilatore C](index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
