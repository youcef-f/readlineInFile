
# Read lines in file

Lire un fichier csv avec un delimiteur **;**  

### Classe main

```java
import java.io.*;

public class app {
	
	public static void main(String[] args) throws NumberFormatException, IOException {
	
		File f = new File("operations.txt");
		FileReader fr = new FileReader(f);
		BufferedReader br = new BufferedReader(fr);

		String line;

		float nombreDeCours = 0;
		float sommeMoyenne = 0;

		while ((line = br.readLine()) != null) {
			nombreDeCours++;
			String[] tabOp = line.split(";");
			sommeMoyenne += Float.parseFloat(tabOp[1]);
		}
		
		
		System.out.println("Moyen:" + sommeMoyenne / nombreDeCours);
		
		br.close();
	}
}
```

### Fichier source 


```bash
> cat operations
math;18
francais;2
anglais;20
music;3
```

### Résultat

```bash
Moyen:10.75
```



