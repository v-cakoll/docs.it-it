---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 3ee94df096b756be544964cfbbd405355e3f728f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581276"
---
# <a name="-delaysign"></a>-delaysign

Specifica se l'assembly avrà firma completa o parziale.

## <a name="syntax"></a>Sintassi

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>Argomenti

`+` &#124; `-`  
Facoltativo. Utilizzare `-delaysign-` se si desidera che l'assembly abbia firma completa. Usare `-delaysign+` se si vuole inserire la chiave pubblica nell'assembly e lo spazio riservato per l'hash firmato. Il valore predefinito è `-delaysign-`.

## <a name="remarks"></a>Osservazioni

L' `-delaysign` opzione non ha alcun effetto a meno che non venga usata con [-](../../../visual-basic/reference/command-line-compiler/keyfile.md) [filecontainer o-filecontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).

Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata. La firma digitale risultante viene archiviata nel file contenente il manifesto. Quando un assembly ha una firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta in un secondo momento.

Usando `-delaysign+`, ad esempio, uno sviluppatore di un'organizzazione può distribuire le versioni di test senza segno di un assembly che i tester possono registrare con il global assembly cache e usare. Al termine dell'operazione sull'assembly, la persona responsabile della chiave privata dell'organizzazione può firmare completamente l'assembly. Questo compartimentazione protegge la chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di lavorare sugli assembly.

Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) .

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Per impostare-delaysign in Visual Studio Integrated Development Environment

1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.

2. Fare clic sulla scheda **Firma** .

3. Impostare il valore nella casella **solo firma ritardata** .

## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
