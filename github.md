# Github

Today I learned about Github and Markdown.

## Text

I learned to use **bold** and *italicized* text.


## Code Blocks

I also learned to create code blocks. The following code defines a 
Powershell function that works similar to the linux base64 function.

```powershell
function base64{
    [CmdletBinding()]
    param(
        [Parameter()]
        [switch]$decode=$FALSE,

        [Parameter()]
        [string]$inputStr,

        [Parameter(ValueFromPipeline)]
        [string]$pipelineStr        
    )
    if($pipelineStr -ne ""){
        $inputStr = $pipelineStr
    }
    $outputStr = ""
    if($decode){        
        $outputStr = [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($inputStr))
    }else{        
        $outputStr = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes($inputStr))
    }
    Write-Host $outputStr
}
```

## Lists

I also learned to create lists

### Ordered

1. Item 1 
2. Item 2
3. Item 3
4. Item 4
5. Item 5

### Unordered

- Item a
- Item b
- Item c
- Item d
- Item e

## Links

Here is a link to my departments website: [UKHC DevOps](https://devops.ukhc.org/).

## Images

I have a good example of an image in the [README.md](https://github.com/Mikie4/syslib-sp2024?tab=readme-ov-file)

## Block Quotes

Finally, I learned to use block quotes.

> They can force you to destroy democracy, but
> they cannot force you to raise the dead.
>
> -- <cite>[Inspirobot](https://inspirobot.me/)</cite>
