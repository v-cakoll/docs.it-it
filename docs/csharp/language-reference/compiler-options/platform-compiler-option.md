---
title: -platform (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 5150e871d75c3c34dab10f10cdac3d8322d7a834
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70849874"
---
# <a name="-platform-c-compiler-options"></a>-platform (opzioni del compilatore C#)

Specifica la versione di Common Language Runtime (CLR) in grado di eseguire l'assembly.

## <a name="syntax"></a>Sintassi

```console
-platform:string
```

## <a name="parameters"></a>Parametri

`string` \
anycpu (impostazione predefinita), anycpu32bitpreferred, ARM, x64, x86 o Itanium.

## <a name="remarks"></a>Osservazioni

- **anycpu** (valore predefinito) consente di compilare l'assembly in modo da poter essere eseguito su qualsiasi piattaforma. L'applicazione viene eseguita come processo a 64 bit, quando possibile, e tramite essa viene eseguito il fallback a 32 bit solo quando questa modalità è disponibile.

- **anycpu32bitpreferred** consente di compilare l'assembly in modo da poter essere eseguito su qualsiasi piattaforma. L'applicazione viene eseguita in modalità a 32 bit nei sistemi che supportano sia le applicazioni a 64 bit sia quelle a 32 bit. È possibile specificare questa opzione solo per i progetti destinati a .NET Framework 4.5.

- **ARM** compila l'assembly in modo da poter essere eseguito su un computer con processore Advanced RISC Machine (ARM).

- **ARM64** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer con un processore Advanced RISC Machine (ARM) che supporta il set di istruzioni A64.

- **x64** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer che supporta il set di istruzioni AMD64 o EM64T.

- **x86** compila l'assembly in modo che possa essere eseguito da CLR a 32 bit, compatibile con x86.

- **Itanium** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer dotato di processore Itanium.

In un sistema operativo Windows a 64 bit:

- Gli assembly compilati con **-platform:x86** vengono eseguiti dalla versione di Common Language Runtime a 32 bit in WOW64.

- Una DLL compilata con l'opzione **-platform:anycpu** viene eseguita dallo stesso Common Language Runtime del processo in cui viene caricata.

- Gli eseguibili compilati con **-platform:anycpu** vengono eseguiti dalla versione di Common Language Runtime a 64 bit.

- Gli eseguibili compilati con l'opzione **-platform:anycpu32bitpreferred** vengono eseguiti dalla versione di Common Language Runtime a 32 bit.

L'impostazione **anycpu32bitpreferred** è valida solo per file eseguibili (con estensione exe) e richiede .NET Framework 4.5.

Per altre informazioni sullo sviluppo di un'applicazione da eseguire su un sistema operativo Windows a 64 bit, vedere [Applicazioni a 64 bit](../../../framework/64-bit-apps.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio

1. Aprire la pagina **Proprietà** del progetto.

2. Fare clic sulla pagina della proprietà **Compilazione**.

3. Modificare la proprietà **Piattaforma di destinazione** e, per i progetti destinati a .NET Framework 4.5, selezionare o deselezionare la casella di controllo **Preferisci 32 bit**.

> [!NOTE]
> `-platform`non è disponibile nell'ambiente di sviluppo in Visual C.

Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.

## <a name="example"></a>Esempio

L'esempio seguente illustra come usare l'opzione **-platform** per specificare che l'applicazione deve essere eseguita dalla versione di Common Language Runtime a 64 bit in un sistema operativo Windows a 64 bit.

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
