---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 66edc45c622b78187469ccc0631beb53b68049b0
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002292"
---
# <a name="-delaysign"></a>-delaysign
Specifica se l'assembly avrà firma completa o parziale.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 facoltativo. Utilizzare `-delaysign-` se si desidera che l'assembly abbia firma completa. Usare `-delaysign+` se si vuole inserire la chiave pubblica nell'assembly e lo spazio riservato per l'hash firmato. Il valore predefinito è `-delaysign-`.  
  
## <a name="remarks"></a>Note  
 L'opzione `-delaysign` non ha alcun effetto a meno che non venga usata con [-filefile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [-container](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata. La firma digitale risultante viene archiviata nel file contenente il manifesto. Quando un assembly ha una firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta in un secondo momento.  
  
 Se ad esempio si usa `-delaysign+`, uno sviluppatore di un'organizzazione può distribuire le versioni di test non firmate di un assembly che i tester possono registrare con la Global Assembly Cache e usare. Al termine dell'operazione sull'assembly, la persona responsabile della chiave privata dell'organizzazione può firmare completamente l'assembly. Questo compartimentazione protegge la chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di lavorare sugli assembly.  
  
 Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) .  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Per impostare-delaysign in Visual Studio Integrated Development Environment  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2. Fare clic sulla scheda **Firma**.  
  
3. Impostare il valore nella casella **solo firma ritardata** .  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
