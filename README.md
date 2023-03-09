# Tímaverkefni 1

## 1. Serial Monitor "Hello World!"

```cpp
void setup() {
  Serial.begin(9600); 

}

void loop() {
  Serial.println("Hello from Arduino");

}
```

## 2. Hello World endurtekið (aftur og aftur)

### 1.

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  for(int k = 0; k < 5; k++) {
    Serial.println("Hello");
  }

  for(int k = 0; k < 5; k++) {
    Serial.println("World");
  }
}
```

### 2.

```cpp
int k = 10;
bool h = true;

void setup() {
  Serial.begin(9600);

}

void loop() {
  if(k % 10 < 5) {
    Serial.println("Hello");
    k++;
  } else {
    Serial.println("World");
    k++;
  };

}
```

## 3. Halló og bless

### 1.

```cpp
char stafur = 0;

void setup() {
  Serial.begin(9600);
  Serial.println("");
}

void loop() {
  if(Serial.available() > 0) {
    stafur = Serial.read();
  }
  if(stafur == 'h') {
    Serial.println("hallo");
  } else if(stafur == 'b') {
    Serial.println("bless");
  }
}
```

### 2.

```cpp
char stafur = 0;

void setup() {
  Serial.begin(9600);
  Serial.println("");
}

void loop() {
  if(Serial.available() > 0) {
    stafur = Serial.read();
  }
  switch (stafur) {
    case 'h':
      Serial.println("hallo");
      break;
    case 'b':
      Serial.println("bless");
      break;
    default:
      Serial.println("Ekki rett val!");
      break;
  }
}
```

## 4. Í hástafi

### 1.

```cpp
void setup() {
  Serial.begin(9600);
  Serial.println("");
}

void loop() {
  String strengur = Serial.readStringUntil('\n');
  strengur.toUpperCase();
  Serial.println(strengur);
  Serial.println("Fjoldi stafa: ");Serial.print(strengur.length());
  Serial.println("\n\n");
}
```

Ef ég myndi vilja láta textann birtast aftur og aftur þá myndi ég nota while lúppu
