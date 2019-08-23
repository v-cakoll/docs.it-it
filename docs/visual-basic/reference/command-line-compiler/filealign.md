---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929477"
---
# <a name="-filealign"></a>-filealign
Specifica la posizione di allineamento per le sezioni del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argomenti  
 `number`  
 Richiesto. Valore che specifica l'allineamento delle sezioni nel file di output. I valori validi sono 512, 1024, 2048, 4096 e 8192. I valori sono in byte.  
  
## <a name="remarks"></a>Note  
 È possibile usare l' `-filealign` opzione per specificare l'allineamento delle sezioni nel file di output. Le sezioni sono blocchi di memoria contigua in un file eseguibile portabile (PE) che contiene il codice o i dati. L' `-filealign` opzione consente di compilare l'applicazione con un allineamento non standard. la maggior parte degli sviluppatori non è necessario utilizzare questa opzione.  
  
 Ogni sezione è allineata a un limite che corrisponde a un `-filealign` multiplo del valore. Non vi è alcun valore predefinito fisso. Se `-filealign` non viene specificato, il compilatore sceglie un valore predefinito in fase di compilazione.  
  
 Specificando le dimensioni della sezione, è possibile modificare le dimensioni del file di output. La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.  
  
> [!NOTE]
> L' `-filealign` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
