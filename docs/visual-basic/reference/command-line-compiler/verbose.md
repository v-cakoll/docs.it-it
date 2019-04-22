---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832792"
---
# <a name="-verbose"></a>-verbose
Indica al compilatore di generare messaggi di stato e di errore dettagliati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativo. Che specifica `-verbose` è uguale a quello ottenuto specificando `-verbose+`, in modo che il compilatore generi i messaggi dettagliati. Il valore predefinito per questa opzione è `-verbose-`.  
  
## <a name="remarks"></a>Note  
 Il `-verbose` opzione Visualizza le informazioni sul numero totale di errori generati dal compilatore, segnala gli assembly vengono caricati da un modulo e consente di visualizzare quali file sono attualmente in fase di compilazione.  
  
> [!NOTE]
>  Il `-verbose` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare informazioni dettagliate sullo stato.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
