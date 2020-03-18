---
title: -filealign (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: aed8b412ea1580f7dfa4f87333598d76a85b5e64
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603018"
---
# <a name="-filealign-c-compiler-options"></a>-filealign (opzioni del compilatore C#)
L'opzione **-filealign** consente di specificare le dimensioni delle sezioni nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argomenti  
 `number`  
 Valore che specifica le dimensioni delle sezioni nel file di output. I valori validi sono 512, 1024, 2048, 4096 e 8192. I valori sono in byte.  
  
## <a name="remarks"></a>Osservazioni  
 Ogni sezione sarà allineata in base a un limite corrispondente multiplo del valore **-filealign**. Non vi è alcun valore predefinito fisso. Se **-filealign** non è specificato, Common Language Runtime sceglie un valore predefinito in fase di compilazione.  
  
 Specificando le dimensioni della sezione, si influisce sulla dimensione del file di output. La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.  
  
 Usare [DUMPBIN](/cpp/build/reference/dumpbin-options) per visualizzare informazioni sulle sezioni nel file di output.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Fare clic sul pulsante **Avanzate**.  
  
4. Modificare la proprietà **Allineamento file**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
