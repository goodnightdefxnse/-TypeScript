class User {
    private _name: string;
    private _login: string;
    private _password: string;
    static count: number = 0;

    constructor(name: string, login: string, password: string) {
        this._name = name;
        this._login = login;
        this._password = password;
        if (this.constructor === User) {
            User.count++;
        }
    }

    get name(): string {
        return this._name;
    }

    set name(value: string) {
        this._name = value;
    }

    get login(): string {
        return this._login;
    }

    get password(): string {
        return "**********";
    }

    set password(value: string) {
        this._password = value;
    }

    showInfo(): void {
        console.log(`Name: ${this.name}, login: ${this.login}`);
    }
}

class SuperUser extends User {
    private _role: string;
    static count: number = 0;

    constructor(name: string, login: string, password: string, role: string) {
        super(name, login, password);
        this._role = role;
        SuperUser.count++;
    }

    get role(): string {
        return this._role;
    }

    set role(value: string) {
        this._role = value;
    }

    showInfo(): void {
        console.log(`Name: ${this.name}, login: ${this.login}, Role: ${this.role}`);
    }
}
