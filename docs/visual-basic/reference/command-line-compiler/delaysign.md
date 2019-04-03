---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: ccf569aea1363d256728e122818b70284a9e250d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830370"
---
# <a name="-delaysign"></a>-delaysign
Specifica se l'assembly avrà firma completa o parziale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Utilizzare `-delaysign-` se si desidera che l'assembly abbia firma completa. Usare `-delaysign+` se si desidera inserire la chiave pubblica nell'assembly e riserva lo spazio per l'hash con segno. Il valore predefinito è `-delaysign-`.  
  
## <a name="remarks"></a>Note  
 Il `-delaysign` opzione non ha effetto solo se abbinata [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oppure [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata. La firma digitale risultante viene archiviata nel file contenente il manifesto. Quando un assembly è impostata la firma ritardata, il compilatore non di calcolo e archiviare la firma, ma riserva lo spazio nel file in modo che la firma può essere aggiunto in un secondo momento.  
  
 Ad esempio, usando `-delaysign+`, uno sviluppatore di un'organizzazione può distribuire le versioni di test senza segno di un assembly che i tester possono registrarsi con la global assembly cache e usare. Al termine di lavoro nell'assembly, la persona responsabile della chiave privata dell'organizzazione possa firmare completamente l'assembly. In questo contesto protegge chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di utilizzare gli assembly.  
  
 Visualizzare [creazione e assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per altre informazioni su come firmare un assembly.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Per impostare - delaysign nell'ambiente di sviluppo integrato di Visual Studio  
  
1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2.  Fare clic sulla scheda **Firma**.  
  
3.  Impostare il valore di **solo firma ritardata** casella.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
