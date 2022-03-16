### [Hi there!](https://twitter.com/alexdaubois/) 👋

```php
class AlexDaubois implements SymfonyDeveloperInterface
{
    public function __construct(
        private string $firstName = 'Alexandre',
        private string $lastName = 'Daubois',
        private \DateTime $birthDate = new \DateTime('1996-01-07T05:30:00+0200')
    ) {
    }
    
    public function getCurrentCompany(): string
    {
        return 'SensioLabs';
    }
    
    public function getCurrentCity(): string
    {
        return 'Lyon, France';
    }
    
    public function isCertified(): bool
    {
        return true;
    }
    
    public function getCertificationLabel(): string
    {
        return 'Symfony 6 Certified Developer (Expert)';
    }
    
    public function getBlog(): ?SocialAccountInterface
    {
        return new MediumPage('https://alex-daubois.medium.com/');
    }
    
    public function getTwitter(): ?SocialAccountInterface
    {
        return new TwitterAccount('https://alex-daubois.medium.com/');
    }
    
    public function getAdditionalLinks(): \Generator
    {
        yield 'https://amv.gallery';
    }
}
```
