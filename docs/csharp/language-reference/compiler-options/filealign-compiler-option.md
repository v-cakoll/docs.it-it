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
ms.openlocfilehash: f3ce1bb864c4cb0b1c330de7d96649f9870231e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328699"
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
  
1. Aprire la pagine **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Fare clic su **Avanzate** .  
  
4. Modificare la proprietà **Allineamento file**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
