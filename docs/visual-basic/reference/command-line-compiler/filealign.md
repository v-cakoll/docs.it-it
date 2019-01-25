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
ms.openlocfilehash: 551d151ab923110c73a528a5def639fb383c889f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715920"
---
# <a name="-filealign"></a>-filealign
Specifica la posizione di allineamento per le sezioni del file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Argomenti  
 `number`  
 Obbligatorio. Un valore che specifica l'allineamento delle sezioni nel file di output. I valori validi sono 512, 1024, 2048, 4096 e 8192. I valori sono in byte.  
  
## <a name="remarks"></a>Note  
 È possibile usare il `-filealign` opzione per specificare l'allineamento delle sezioni nel file di output. Le sezioni sono blocchi di memoria contigua in un file eseguibile portabile (PE) che contiene codice né dati. Il `-filealign` opzione consente di compilare l'applicazione con un allineamento non standard, la maggior parte degli sviluppatori non sono necessario usare questa opzione.  
  
 Ogni sezione è allineato in base a un limite è un multiplo di `-filealign` valore. Non vi è alcun valore predefinito fisso. Se `-filealign` non viene specificato, il compilatore sceglie un valore predefinito in fase di compilazione.  
  
 Specifica le dimensioni della sezione, è possibile modificare le dimensioni del file di output. La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.  
  
> [!NOTE]
>  Il `-filealign` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
