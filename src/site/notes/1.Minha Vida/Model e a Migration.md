---
{"Title":"Criando a Model e a Migration","created":"2024-11-11","dg-publish":true,"tags":["pessoal/estudos","pessoal/quaseumdev"],"permalink":"/1-minha-vida/model-e-a-migration/","dgPassFrontmatter":true}
---

| [Voltar](index) |
### **Criando a Model e a Migration**
No terminal, execute:
```bash
php artisan make:model Product -m
```
Este comando cria a model `Product` e a migration `create_products_table`. Em seguida, defina os atributos e relacionamentos na model e configure as colunas desejadas na migration.

>**Dica**: Inclua sempre as propriedades `$fillable` na model para segurança de atribuição em massa.
``` php
class Product extends Model
{
    protected $fillable = ['name', 'price', 'description', 'stock'];
}
```
Na migration, configure as colunas com os tipos de dados adequados:
```php
Schema::create('products', function (Blueprint $table) {
    $table->id();
    $table->string('name');
    $table->decimal('price', 8, 2);
    $table->text('description')->nullable();
    $table->integer('stock')->default(0);
    $table->timestamps();
});
```

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/3-caixa-de-entrada/migrates/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




| [Voltar](index) |

### **Criar a tabela relacionada (com chave estrangeira):**

Na tabela relacionada, você deve incluir a chave estrangeira referenciando a tabela principal. Por exemplo, para uma tabela de "posts" relacionada a "users":

```php
Schema::create('posts', function (Blueprint $table) {
    $table->id();
    $table->string('title');
    $table->text('content');
    $table->foreignId('user_id') 
    // Cria a coluna `user_id` com a referência automática
          ->constrained('users') 
          // Refere-se à tabela `users` pela coluna `id`
          ->onDelete('cascade'); 
          // Configura para deletar posts se o usuário for excluído
    $table->timestamps();
});

```

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/3-caixa-de-entrada/model/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




| [Voltar](index) |
## Exemplo de Relacionamento `One to Many` (Um para Muitos):
#### **Modelo `User`:**
O modelo `User` representa o "lado pai" do relacionamento.
```php
class User extends Model
{
    use HasFactory;

    // Relacionamento: Um usuário tem muitos posts
    public function posts()
    {
        return $this->hasMany(Post::class);
    }
}
```
#### **Modelo `Post`:**
O modelo `Post` representa o "lado filho" do relacionamento.
```php
class Post extends Model
{
    use HasFactory;

    // Relacionamento: Um post pertence a um usuário
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}

```

</div></div>


</div></div>

