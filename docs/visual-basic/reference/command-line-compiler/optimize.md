---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397441"
---
# <a name="-optimize"></a>-optimize
Abilita o Disabilita le ottimizzazioni del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativa. L' `-optimize-` opzione Disabilita le ottimizzazioni del compilatore. L' `-optimize+` opzione consente le ottimizzazioni. Per impostazione predefinita, le ottimizzazioni sono disabilitate.|  
  
## <a name="remarks"></a>Commenti  
 Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente. Tuttavia, poiché le ottimizzazioni generano una riorganizzazione del codice nel file di output, `-optimize+` può rendere difficile il debug.  
  
 Tutti i moduli generati con `-target:module` per un assembly devono usare le stesse `-optimize` impostazioni dell'assembly. Per ulteriori informazioni, vedere [-target (Visual Basic)](target.md).  
  
 È possibile combinare le `-optimize` `-debug` Opzioni e.  
  
|Per impostare-optimize in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />     <br />2. fare clic sulla scheda **Compila** .<br />3. fare clic sul pulsante **Avanzate** .<br />4. modificare la casella di controllo **Abilita ottimizzazioni** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e Abilita le ottimizzazioni del compilatore.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [-debug (Visual Basic)](debug.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [-target (Visual Basic)](target.md)
