---
title: -define (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 4a3622b6acc8ebe9c590b01b67074ae59396fc34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173744"
---
# <a name="-define-c-compiler-options"></a>-define (opzioni del compilatore C#)
L'opzione **-define** definisce `name` come simbolo in tutti i file del codice sorgente nel programma.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a>Argomenti  
 `name`, `name2`  
 Nome di uno o più simboli che si vuole definire.  
  
## <a name="remarks"></a>Osservazioni  
 L'opzione **-define** ha lo stesso effetto dell'uso di una direttiva [#define](../preprocessor-directives/preprocessor-define.md) per il preprocessore, ad eccezione del fatto che l'opzione del compilatore è valida per tutti i file nel progetto. Un simbolo resta definito in un file del codice sorgente finché una direttiva [#undef](../preprocessor-directives/preprocessor-undef.md) nel file non rimuove la definizione. Quando si usa l'opzione -define, una direttiva `#undef` in un file non ha effetto in altri file del codice sorgente nel progetto.  
  
 È possibile usare i simboli creati da questa opzione con [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md) e [#endif](../preprocessor-directives/preprocessor-endif.md) per la compilazione condizionale dei file del codice sorgente.  
  
 **-d** è la versione abbreviata di **-define**.  
  
 È possibile definire più simboli con **-define** separando i nomi di simbolo con virgole o punti e virgola. Ad esempio:  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 Il compilatore C# stesso non definisce alcun simbolo o macro che è possibile usare nel codice sorgente. Tutte le definizioni dei simboli devono essere definite dall'utente.  
  
> [!NOTE]
> `#define` in C# non consente di assegnare un valore a un simbolo, diversamente dai linguaggi come C++. Ad esempio, non è possibile usare `#define` per creare una macro o per definire una costante. Se è necessario definire una costante, usare una variabile `enum`. Se si vuole creare una macro in stile C++, prendere in considerazione altre alternative, ad esempio i generics. Poiché le macro sono notoriamente soggette a errori, C# non ne consente l'uso, ma offre alternative più sicure.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagina **Proprietà** del progetto.  
  
2. Nella scheda **Compila** digitare il simbolo che deve essere definito nella casella **Simboli di compilazione condizionale**. Se si usa l'esempio di codice seguente, ad esempio, digitare `xx` nella casella di testo.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## <a name="example"></a>Esempio  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test
{  
    public static void Main()
    {  
        #if (xx)
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
