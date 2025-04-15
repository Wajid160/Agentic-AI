# Python UV

[Python UV: Sabse Tez Python Package Manager ke liye Ultimate Guide](https://www.datacamp.com/tutorial/python-uv)  
[Official Docs](https://docs.astral.sh/uv/)  
[Scripts Chalana](https://docs.astral.sh/uv/guides/scripts/)  
[Projects pe Kaam Karna](https://docs.astral.sh/uv/guides/projects/)  
[CLI Reference](https://docs.astral.sh/uv/reference/cli/)  
[Dekhein: Python Setup, Asaan Kiya Gaya: Ek Poora "uv" Tutorial!](https://www.youtube.com/watch?v=-J5SnWR4UXw)  

## Cursor Rules:

Jab bhi Python mein kaam karo, hamesha UV ko package manager ke tor pe use karo.  

Code likhne ke bajaye, jab efficient ho toh CLI commands use kar sakte ho, jaise jab naye project ke liye kaha jaye toh UV ke saath yeh karo:  

**Packaged Applications**  
Boht se use-cases ke liye ek package chahiye hota hai. Masalan, agar aap ek command-line interface bana rahe ho jo PyPI pe publish hoga ya agar aap tests ek alag directory mein define karna chahte ho.  

--package flag ke saath ek packaged application banayi ja sakti hai:  

    uv init --package example-pkg  

Aur project mein packages install karne ke liye:  

Dependency add karne ke liye:  

    uv add crewai  

---

# UV Project Banayein aur VS Code Setup Karein  

    uv version  

    uv help  

    uv init --package explore-uv  

Yeh command ek project banata hai jo packaging ke liye structured hota hai, aapka code src directory mein rakhta hai, jo Python project structures ke best practices ke saath hai.  

    cd explore-uv  

    code .  

Terminal pe `code .` use karein ya explore-uv directory ko VSCode mein kholein.  

Ab virtual environment banayein:  

    uv venv  

Virtual environment activate karein:  

    source .venv/bin/activate  

    Windows mein:  
    \explore-uv\.venv\Scripts\activate  

VSCode mein virtual environment ke dwara banaye gaye recommended Python interpreter (./.venv/bin/python) ko select karein.  

    uv run explore-uv