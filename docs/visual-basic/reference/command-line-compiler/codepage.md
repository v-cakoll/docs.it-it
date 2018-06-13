---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 383b6adae94c27efdd236de31ddfa8d16a6d4648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648528"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`id`|Obbligatorio. Il compilatore Usa la tabella codici specificata da `id` per interpretare la codifica dei file di origine.|  
  
## <a name="remarks"></a>Note  
 Per compilare codice sorgente salvato con una codifica specifica, è possibile utilizzare `-codepage` per specificare la tabella codici da utilizzare. Il `-codepage` opzione si applica a tutti i file di codice sorgente nella compilazione. Per ulteriori informazioni, vedere [codifica dei caratteri in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 Il `-codepage` opzione non è necessaria se sono stati salvati i file di codice sorgente utilizzando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma. Visual Studio Salva tutti i file del codice sorgente con la tabella codici ANSI corrente per impostazione predefinita, a meno che l'utente specifica un'altra codifica nel **codifica** finestra di dialogo. Visual Studio Usa il **codifica** finestra di dialogo per aprire i file di codice sorgente salvati con una tabella codici diversa.  
  
> [!NOTE]
>  Il `-codepage` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
