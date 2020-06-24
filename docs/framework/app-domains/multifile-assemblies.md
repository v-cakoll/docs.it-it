---
title: Assembly su più file
description: Usare gli assembly su più file destinati a .NET con i compilatori della riga di comando o Visual Studio con Visual C++. Un file nell'assembly deve conservare il manifesto dell'assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104631"
---
# <a name="multifile-assemblies"></a>Assembly su più file

È possibile creare assembly su più file destinati ai .NET Framework usando compilatori della riga di comando o Visual Studio con Visual C++. Un file all'interno dell'assembly deve contenere il manifesto dell'assembly. Un assembly che avvia un'applicazione deve contenere anche un punto di ingresso, ad esempio `Main` un `WinMain` metodo o.

Si supponga, ad esempio, di disporre di un'applicazione che contiene due moduli di codice, *client.cs* e *Stringer.cs*. *Stringer.cs* crea lo `myStringer` spazio dei nomi a cui fa riferimento il codice in *client.cs*. *Client.cs* contiene il `Main` metodo, che è il punto di ingresso dell'applicazione. In questo esempio vengono compilati i due moduli di codice e quindi viene creato un terzo file contenente il manifesto dell'assembly che avvia l'applicazione. Il manifesto dell'assembly fa riferimento ai moduli *client* e *Stringer* .

> [!NOTE]
> Negli assembly su più file può essere presente un solo punto di ingresso, anche se l'assembly include più moduli di codice.

La scelta di creare un assembly su più file può essere consigliabile per varie ragioni:

- Per combinare moduli scritti in linguaggi diversi. Questo è il motivo più comune per la creazione di un assembly su più file.

- Per ottimizzare il download di un'applicazione inserendo i tipi usati raramente in un modulo che verrà scaricato solo quando necessario.

    > [!NOTE]
    > Se si creano applicazioni che verranno scaricate usando il tag `<object>` con Microsoft Internet Explorer, è importante creare assembly su più file. In questo scenario occorrerà creare un file separato dai moduli di codice che contenga solo il manifesto dell'assembly. Internet Explorer scarica prima il manifesto dell'assembly e quindi crea i thread di lavoro per scaricare altri moduli o assembly eventualmente necessari. Durante il download del file che contiene il manifesto dell'assembly, Internet Explorer non risponde all'input dell'utente. Tanto minori saranno le dimensioni del file contenente il manifesto dell'assembly, tanto più breve sarà il tempo in cui Internet Explorer non risponderà.

- Per combinare moduli di codice scritti da più sviluppatori. Sebbene ogni sviluppatore possa compilare ogni modulo di codice in un assembly, questa operazione può forzare l'esposizione pubblica di alcuni tipi che non sarebbero esposti se tutti i moduli venissero inclusi in un assembly su più file.

Una volta creato l'assembly, è possibile firmare il file contenente il manifesto dell'assembly e, di conseguenza, l'assembly, oppure è possibile assegnare un nome sicuro al file e all'assembly e inserirlo nell'Global Assembly Cache.

## <a name="see-also"></a>Vedi anche

- [Procedura: Creare un assembly su più file](build-multifile-assembly.md)
- [Programmare con gli assembly](../../standard/assembly/index.md)
